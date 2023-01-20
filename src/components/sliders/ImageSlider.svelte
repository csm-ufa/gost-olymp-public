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
  
    let thumbsSwiper = null;
    const images = [
        { url: "/assets/image0.jpg.webp", alt: "" },
        { url: "/assets/image1.jpg.webp", alt: "" },
        { url: "/assets/image2.jpg.webp", alt: "" },
        { url: "/assets/image3.jpg.webp", alt: "" },
        { url: "/assets/image4.jpg.webp", alt: "" },
        { url: "/assets/image5.jpg.webp", alt: "" },
        { url: "/assets/image6.jpg.webp", alt: "" },
        { url: "/assets/image7.jpg.webp", alt: "" },
        { url: "/assets/image8.jpg.webp", alt: "" },
        { url: "/assets/image9.jpg.webp", alt: "" },
        { url: "/assets/image10.jpg.webp", alt: "" },
        { url: "/assets/image11.jpg.webp", alt: "" },
        { url: "/assets/image12.jpg.webp", alt: "" },
        { url: "/assets/image13.jpg.webp", alt: "" },
        { url: "/assets/image14.jpg.webp", alt: "" },
        { url: "/assets/image15.jpg.webp", alt: "" },
        { url: "/assets/image16.jpg.webp", alt: "" },
        { url: "/assets/image17.jpg.webp", alt: "" },
    ]
  
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
  