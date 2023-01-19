<script>
    import { fade } from 'svelte/transition';
    import { Swiper, SwiperSlide } from "swiper/svelte";
    import { Pagination, Navigation, Mousewheel } from "swiper";
    import "swiper/css";
    import "swiper/css/pagination";
    import "swiper/css/navigation";

    export let height = "600px";
    export let animation = { delay: 150, duration: 300 };
    export let data = [{
        styles: ``,
        title: `<h2>ЗАГОЛОВОК</h2>`,
        content: `<p>Контент</p>`,
    }];

    let swiperInstance = null;
    let activeIndex = 0;
    let mouseActive = false;
    
    const initSwiper = (swiper) => swiperInstance = swiper.detail[0];
    const mouseActivate = () => {
        mouseActive = true;
        return swiperInstance.mousewheel.enable()
    }
    const slideChange = () => {
        mouseActive = true;
        activeIndex = swiperInstance.activeIndex
        if ( activeIndex >= data.length - 1 && mouseActive) {
            const timerB = setTimeout(() => {
                clearTimeout(timerB)
                return swiperInstance.mousewheel.disable()
            }, 300)
        }
    };
</script>

<div class="h-[500px] relative"  on:mouseleave={mouseActivate} on:click={mouseActivate} on:keydown={({key}) => key = "Enter" && mouseActivate}>
    <Swiper
        on:init={initSwiper}
        on:slideChange={slideChange}
        direction={"horizontal"}
        pagination={{
            type: "progressbar",
        }}
        autoHeight={true}
        navigation={true}
        mousewheel={true}
        slidesPerView={1}
        spaceBetween={10}
        modules={[Pagination, Navigation, Mousewheel]}
        class="z-10"
    >
        {#each data as slide, index }
            <SwiperSlide>
                <svelte:component this={slide.component} reverse={index % 2} styles="{slide.styles} w-full relative h-[{ height }]">
                    <span slot="title">
                        {#if activeIndex >= index }
                            <span transition:fade={animation}>
                                { @html slide.title }
                            </span>
                        {/if}
                    </span>
                    <span slot="content">
                        {#if activeIndex >= index }
                            <span transition:fade={{...animation, delay: 250}}>
                                { @html slide.content }
                            </span>
                        {/if}
                    </span>
                </svelte:component>
            </SwiperSlide>            
        {/each}
    </Swiper>
</div>