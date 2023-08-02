<script>
    import { Swiper, SwiperSlide } from "swiper/svelte";
  
    // Import Swiper styles
    import "swiper/css";
  
    import "swiper/css/free-mode";
    import "swiper/css/navigation";
    import "swiper/css/thumbs";
    import "swiper/css/lazy";
  
  
    // import required modules
    import { Lazy, FreeMode, Navigation, Thumbs } from "swiper";
    export let images = [];
    let thumbsSwiper = null;
  
    const setThumbsSwiper = (e) => {
      const [swiper] = e.detail;
      // set Thumbs swiper instance
      setTimeout(() => {
            thumbsSwiper = swiper;
      });
    };
</script>
  
<div class="relative xl:h-[550px]">
    <Swiper
        style="--swiper-navigation-color: #444;--swiper-pagination-color: #444"
        spaceBetween={10}
        navigation={true}
        lazy={true}
        thumbs={{ swiper: thumbsSwiper }}
        modules={[Lazy, FreeMode, Navigation, Thumbs]}
        class="mySwiper2"
        >
        {#if images.length}
            {#each images as { url, alt }, index }
                <SwiperSlide>
                    <div class="flex justify-center select-none">
                        <img src="{url}" alt="{alt || index}" class="h-[500px] select-none swiper-lazy" loading="lazy" />
                    </div>
                    <div class="swiper-lazy-preloader swiper-lazy-preloader-white" />
                </SwiperSlide>
            {/each}
        {/if}
    </Swiper>
</div>
<Swiper
    on:swiper={setThumbsSwiper}
    spaceBetween={10}
    slidesPerView={5}
    freeMode={true}
    lazy={true}
    watchSlidesProgress={true}
    modules={[Lazy, FreeMode, Navigation, Thumbs]}
    class="mySwiper"
>
    {#if images.length}
        {#each images as { url, alt }, index }
            <SwiperSlide>
                <img src="{url}" alt="{alt || index}" class="h-[175px] cursor-pointer swiper-lazy" loading="lazy"/>
                <div class="swiper-lazy-preloader swiper-lazy-preloader-white" />
            </SwiperSlide>
        {/each}
    {/if}
</Swiper>
  