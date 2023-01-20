<script>
	import Container from "./Container.svelte";
</script>

<section>
    <Container>
        <h1 class="focus:outline-none xl:mt-20 text-4xl lg:text-5xl xl:text-6xl font-extrabold text-center leading-10 text-gray-800 dark:text-white w-full mb-10">
            Отзывы участников
        </h1>
        <div class="flex flex-wrap justify-center items-center">
            <div class="w-full lg:w-1/2 xl:w-1/4 p-2">
                <img src="/img/review_1.jpeg" loading="lazy" data-zimg="true" alt="отзыв об олимпиаде " class="h-[320px] lg:h-auto mx-auto cursor-pointer rounded-2xl filter grayscale hover:grayscale-0 shadow-lg shadow-gray-300 hover:shadow-none hover:rounded duration-200 transition-all">
            </div>
            <div class="w-full lg:w-1/2 xl:w-1/4 p-2">
                <img src="/img/review_2.jpeg" loading="lazy" data-zimg="true" alt="отзыв об олимпиаде " class="h-[320px] lg:h-auto mx-auto cursor-pointer rounded-2xl filter grayscale hover:grayscale-0 shadow-lg shadow-gray-300 hover:shadow-none hover:rounded duration-200 transition-all">
            </div>
            <div class="w-full lg:w-1/2 xl:w-1/4 p-2">
                <img src="/img/review_3.jpeg" loading="lazy" data-zimg="true" alt="отзыв об олимпиаде " class="h-[320px] lg:h-auto mx-auto cursor-pointer rounded-2xl filter grayscale hover:grayscale-0 shadow-lg shadow-gray-300 hover:shadow-none hover:rounded duration-200 transition-all">
            </div>
            <div class="w-full lg:w-1/2 xl:w-1/4 p-2">
                <img src="/img/review_4.jpeg" loading="lazy" data-zimg="true" alt="отзыв об олимпиаде " class="h-[320px] lg:h-auto mx-auto cursor-pointer rounded-2xl filter grayscale hover:grayscale-0 shadow-lg shadow-gray-300 hover:shadow-none hover:rounded duration-200 transition-all">
            </div>
            
        </div>
    </Container>
</section>