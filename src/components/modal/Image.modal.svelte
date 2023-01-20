<script>
    import { createEventDispatcher } from 'svelte';
	import Modal from "./Modal.svelte";
    import Fa from 'svelte-fa/src/fa.svelte';
    import { faClose } from '@fortawesome/free-solid-svg-icons';

    const dispatch = new createEventDispatcher();
    
    export let props = {
        show: false,
        url: '',
        title: ""
    }

    function closeEvent(){
        return dispatch('close', { value: true })
    }
</script>

<Modal show={ props.show } on:close={ closeEvent }>
    <div slot="title">
        <div class="w-full flex flex-nowrap justify-between pr-1 items-center">
            <p class="text-gray-600 font-light">{props.title}</p>
            <span on:click={closeEvent} on:keypress={null} class="px-3 py-2 border border-gray-500 text-gray-500 rounded-lg hover:bord-red-700 hover:bg-red-700 hover:text-white cursor-pointer">
                <Fa icon={faClose} size="xl"/>
            </span>
        </div>
    </div>
    <div slot="body" class="xl:max-w-5xl relative">
        <img src="{props.url}" alt="zoomed-img" class="w-full h-full rounded-2xl" loading="lazy">
    </div>
</Modal>