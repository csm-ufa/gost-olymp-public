<script>
	import Container from "./Container.svelte";
    import Fa from 'svelte-fa/src/fa.svelte';
    import { faArrowUpRightFromSquare } from '@fortawesome/free-solid-svg-icons';
</script>

<section>
    <Container>
        <h1 class="focus:outline-none xl:mt-20 text-4xl lg:text-5xl xl:text-6xl font-extrabold text-center leading-10 text-gray-800 dark:text-white w-full mb-10">
            СМИ о "Молодежной Олимпиаде Стандартов 2022"
        </h1>
        <div class="flex flex-wrap justify-between items-center">
            <div class="w-full lg:w-1/3 mb-5">
                <a 
                class="p-5 mx-2 leading-none flex-row flex-wrap border border-blue-500 hover:text-blue-700 hover:border-blue-700 font-light rounded-xl flex items-center justify-between text-blue-600 text-xl"
                    href="https://bash.news/news/177906-v-ufe-proshla-pervaya-vserossiyskaya-olimpiada-standartov" 
                    target="_blank" rel="noreferrer">
                    <span class="w-full font-normal">Республика Башкортостан</span>
                    <span class="w-1/2 mb-2 text-gray-500 font-thin text-sm">bash.news</span>
                    <Fa icon={faArrowUpRightFromSquare} size="sm"/>
                </a>
            </div>
            <div class="w-full lg:w-1/3 mb-5">
                <a 
                    class="p-5 mx-2 leading-none flex-row flex-wrap border border-blue-500 hover:text-blue-700 hover:border-blue-700 font-light rounded-xl flex items-center justify-between text-blue-600 text-xl"
                    href="https://gtrkamur.ru/news/2022/09/29/258257" 
                    target="_blank" rel="noreferrer">
                    <span class="w-full font-normal">Амурская Область</span>
                    <span class="w-1/2 mb-2 text-gray-500 font-thin text-sm">gtrkamur.ru</span>
                    <Fa icon={faArrowUpRightFromSquare} size="sm"/>
                </a>
            </div>
            <div class="w-full lg:w-1/3 mb-5">
                <a 
                    class="p-5 mx-2 leading-none flex-row flex-wrap border border-blue-500 hover:text-blue-700 hover:border-blue-700 font-light rounded-xl flex items-center justify-between text-blue-600 text-xl"
                    href="https://www.bashinform.ru/news/social/2022-06-01/shkolnik-iz-ufy-v-sostave-sbornoy-strany-primet-uchastie-v-olimpiade-po-standartizatsii-v-yuzhnoy-koree-2825558" 
                    target="_blank" rel="noreferrer">
                    <span class="w-full font-normal">Башинформ</span>
                    <span class="w-1/2 mb-2 text-gray-500 font-thin text-sm">bashinform.ru</span>
                    <Fa icon={faArrowUpRightFromSquare} size="sm"/>
                </a>
            </div>
            <div class="w-full lg:w-1/3 mb-5">
                <a 
                    class="p-5 mx-2 leading-none flex-row flex-wrap border border-blue-500 hover:text-blue-700 hover:border-blue-700 font-light rounded-xl flex items-center justify-between text-blue-600 text-xl"
                    href="https://rutube.ru/video/e60a1779d4aa3c81d0d901cb0d1e3237/?playlist=97517" 
                    target="_blank" rel="noreferrer">
                    <span class="w-full font-normal">Телеканал "Волга"</span>
                    <span class="w-1/2 mb-2 text-gray-500 font-thin text-sm">gtrkamur.ru</span>
                    <Fa icon={faArrowUpRightFromSquare} size="sm"/>
                </a>
            </div>
            <div class="w-full lg:w-1/3 mb-5">
                <a 
                    class="p-5 mx-2 leading-none flex-row flex-wrap border border-blue-500 hover:text-blue-700 hover:border-blue-700 font-light rounded-xl flex items-center justify-between text-blue-600 text-xl"
                    href="https://dzen.ru/video/watch/62f373ea0dd0245ae5f3ff34?f=video" 
                    target="_blank" rel="noreferrer">
                    <span class="w-full font-normal">Вся Уфа</span>
                    <span class="w-1/2 mb-2 text-gray-500 font-thin text-sm">https://allufa.ru/</span>
                    <Fa icon={faArrowUpRightFromSquare} size="sm"/>
                </a>
            </div>
            <div class="w-full lg:w-1/3 mb-5">
                <a 
                    class="p-5 mx-2 leading-none flex-row flex-wrap border border-blue-500 hover:text-blue-700 hover:border-blue-700 font-light rounded-xl flex items-center justify-between text-blue-600 text-xl"
                    href="https://vk.com/video-27097047_456257037" 
                    target="_blank" rel="noreferrer">
                    <span class="w-full font-normal">БСТ</span>
                    <span class="w-1/2 mb-2 text-gray-500 font-thin text-sm">https://bash.news/bst</span>
                    <Fa icon={faArrowUpRightFromSquare} size="sm"/>
                </a>
            </div>
        </div>
    </Container>
</section>