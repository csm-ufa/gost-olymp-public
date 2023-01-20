<script>
    import { createEventDispatcher, onMount } from 'svelte';

    export let show = false;
    export let params;    
    const dispatch = new createEventDispatcher();
  
    function closeModalEcs({key}){
        if (key === "Escape"){
            return closeEvent()
        }
    }

    function closeEvent(){
        dispatch('close', { value: true })
    }
    
    onMount(()=>{
        return show
            ? window.addEventListener('keydown', closeModalEcs)
            : window.removeEventListener('keydown', closeModalEcs)
    })
</script>
<svelte:window on:keydown={closeModalEcs} />

{#if show}
    <div class="relative z-50" aria-labelledby="modal-title">
        <div class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity"></div>
        <div class="fixed z-50 inset-0 overflow-y-auto">
            <div on:click|self={closeEvent} on:keydown={closeModalEcs} class="flex items-end sm:items-center justify-center min-h-full p-4 text-center sm:p-0">
                <div class="relative bg-white rounded-lg text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:max-w-lg sm:w-full lg:max-w-7xl lg:w-auto xl:max-h-full">
                    <div class="bg-white px-4 pt-5 pb-4 sm:p-6 sm:pb-4">
                        <div class="flex flex-col">
                            <div class="flex justify-start flex-nowrap w-full">
                                <div class="mx-auto flex-shrink-0 mb-2 flex items-center justify-center h-12 w-12 rounded-full bg-gray-100 sm:mx-0 ">
                                    <!-- ICONS -->
                                    <slot name="icon">
                                    </slot>
                                </div>
                                <h3 class="text-lg ml-4 leading-6 font-medium text-gray-900 w-full" id="modal-title">
                                    <!-- TITLE -->
                                    <slot name="title">
                                        {params?.error ? params.error : params?.title || "заголовок"}
                                    </slot>
                                </h3>
                            </div>
                            <div class="mt-3 text-center sm:mt-0 sm:ml-4 sm:text-left">
                                <div class="mt-2">
                                    <!-- BODY -->
                                    <slot name="body"> 
                                        {params?.message || "текст модального окна"}
                                    </slot>
                                </div>
                                <!-- ADDICTION BODY -->
                                <slot></slot>
                            </div>
                        </div>
                    </div>
                    <div class="bg-gray-50 py-3 sm:px-4 sm:flex sm:flex-row-reverse">
                        <slot name="buttons">
                        </slot>
                    </div>
                </div>
            </div>
        </div>
    </div>
{/if}
