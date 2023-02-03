<script>
    import { createEventDispatcher } from 'svelte';
	import Modal from "./Modal.svelte";
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
        <h2 class="text-gray-700 font-bold text-5xl">Условия участия</h2> 
    </div>
    <div slot="body" class="max-w-5xl">
        <p class="text-xl text-gray-800 py-2.5">
            Школьники оцениваются по различным критериям – понимание темы, творческий подход к решению задач, креативное мышление. 
            Обязательное условие - <b><abbr title="Достаточно уровня A2" class="cursor-help" >знание английского языка (A2/B1)</abbr></b>. <br>
            Принять участие может любой школьник в возрасте от 13 до 18 лет. 
        </p>
        <p class="text-xl text-gray-800 py-2.5">
            <b>Отборочный тур </b> начинается с 20 января и продлится до 19 марта. <br>
            <b>Финальный этап </b> состоится 26 апреля в Нижнем Новгороде. 
        </p>
        <p class="text-xl text-gray-800 py-2.5">
            Для участия необходимо: <br>
            <span class="pl-5">1. заполнить <a href="/docs/anketa.doc" content-type="application/msword" download="анкета.doc" class="text-blue-600 underline" rel="preload"> анкету</a> ;</span><br>
            <span class="pl-5">2. написать эссе на тему: <abbr title="ограничений по теме и размеру организаторами не предусмотрено" class="cursor-help">«Для чего нужны стандарты»</abbr>.</span><br>
        </p>
        <p class="text-xl text-gray-800 py-2.5">
            Оба документа отправить на почту  <a href="mailto:olymp@rst.gov.ru" class="text-blue-600 underline">olymp@rst.gov.ru</a>
        </p>
    </div>
</Modal>
