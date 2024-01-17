<script>
    import { createEventDispatcher } from 'svelte';
	import Modal from "./Modal.svelte";
    import Fa from 'svelte-fa/src/fa.svelte';
    import { faFilePdf } from '@fortawesome/free-solid-svg-icons';
	import SocialMedia from '../SocialMedia.svelte';
    const dispatch = new createEventDispatcher();
    
    export let props = {
        show: false
    };
    function closeEvent(){
        return dispatch('close', { value: true })
    }
</script>

<Modal show={ props.show } on:close={ closeEvent }>
    <div slot="title">
        <h2 class="text-gray-700 font-bold text-5xl">Информация и Контакты</h2> 
    </div>
    <div slot="body" class="max-w-5xl text-center">
        <!-- <p class="text-xl text-gray-800 py-2.5">
            Школьники оцениваются по различным критериям – понимание темы, творческий подход к решению задач, креативное мышление. 
            Обязательное условие - <b><abbr title="Достаточно уровня A2" class="cursor-help" >знание английского языка (A2/B1)</abbr></b>. <br>
            Принять участие может любой школьник в возрасте от 13 до 18 лет. 
        </p>
        <p class="text-xl text-gray-800 py-2.5">
            <b>Отборочный тур </b> начинается с 20 января и продлится до 19 марта. <br>
            <b>Финальный этап </b> состоится 12 мая в Нижнем Новгороде. 
        </p> -->
        <p class="text-xl text-gray-800 py-2.5">
            Email по вопросам и предложениям: <br> <a href="mailto:olymp@rst.gov.ru" class="text-blue-600 underline">olymp@rst.gov.ru</a>
        </p>
        <p class="text-xl text-gray-800 py-2.5">
            Положение о конкурсе: 
        </p>
       <div class="flex-row w-full justify-center">
            <a href="/docs/contest_right.pdf" content-type="application/pdf" target="_blank" rel="noreferrer" class="inline-flex w-1/2 hover:bg-blue-700 transition-colors flex-nowrap flex-row justify-start text-white rounded-xl leading-none bg-blue-500 p-4">
                <span class="w-auto mr-4 relative">
                    <Fa icon={faFilePdf} size="3x"/>
                </span>
                <span class="relative">
                    Положение об организации и проведении российского отборочного этапа Молодежной олимпиады стандартов
                </span>
            </a>
            <div></div>
       </div>
        <SocialMedia />
    </div>
</Modal>
