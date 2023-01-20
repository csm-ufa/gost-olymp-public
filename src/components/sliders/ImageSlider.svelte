<script>
    import { Swiper, SwiperSlide } from "swiper/svelte";
  
    // Import Swiper styles
    import "swiper/css";
  
    import "swiper/css/free-mode";
    import "swiper/css/navigation";
    import "swiper/css/thumbs";
  
  
    // import required modules
    import { FreeMode, Navigation, Thumbs } from "swiper";
  
    let thumbsSwiper = null;
    const images = [
        { url: "/assets/image0.jpg", alt: "" },
        { url: "/assets/image1.jpg", alt: "" },
        { url: "/assets/image2.jpg", alt: "" },
        { url: "/assets/image3.jpg", alt: "" },
        { url: "/assets/image4.jpg", alt: "" },
        { url: "/assets/image5.jpg", alt: "" },
        { url: "/assets/image6.jpg", alt: "" },
        { url: "/assets/image7.jpg", alt: "" },
        { url: "/assets/image8.jpg", alt: "" },
        { url: "/assets/image9.jpg", alt: "" },
        { url: "/assets/image10.jpg", alt: "" },
        { url: "/assets/image11.jpg", alt: "" },
        { url: "/assets/image12.jpg", alt: "" },
        { url: "/assets/image13.jpg", alt: "" },
        { url: "/assets/image14.jpg", alt: "" },
        { url: "/assets/image15.jpg", alt: "" },
        { url: "/assets/image16.jpg", alt: "" },
        { url: "/assets/image17.jpg", alt: "" },
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
        style="--swiper-navigation-color: #fff;--swiper-pagination-color: #fff"
        spaceBetween={10}
        navigation={true}
        thumbs={{ swiper: thumbsSwiper }}
        modules={[FreeMode, Navigation, Thumbs]}
        class="mySwiper2"
        >
        {#if images.length}
            {#each images as { url, alt }, index }
                <SwiperSlide>
                    <div class="flex justify-center ">
                        <img src="{url}" alt="{alt || index}" class="h-[500px]" loading="lazy"/>
                    </div>
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
    watchSlidesProgress={true}
    modules={[FreeMode, Navigation, Thumbs]}
    class="mySwiper"
>
    {#if images.length}
        {#each images as { url, alt }, index }
            <SwiperSlide>
                <img src="{url}" alt="{alt || index}" class="h-[175px] cursor-pointer" loading="lazy"/>
            </SwiperSlide>
        {/each}
    {/if}
</Swiper>
  