<script>
    import { createEventDispatcher } from 'svelte';
    export let list = [];

    const dispatch = new createEventDispatcher();
    function linkEvent({target}){
        if (target.hasAttribute('href')){
            const targetIndex = target.dataset.index;
            dispatch('link', { link: target.href, ...list[targetIndex] })
        }
    }
</script>

<nav class="inline-flex justify-end w-full" on:click={ linkEvent } on:keydown={null} id="nav-list">
    {#if list.length }
        {#each list as a, ind }
            <a 
                tabindex="{ind + 1}"
                data-index={ind}
                href={ a.href } 
                class="{[               
                    'text-lg ml-5 px-5 py-2.5 box-border rounded-3xl ',
                    ind + 1 === list.length 
                        ? " bg-indigo-600 text-white hover:text-white hover:bg-indigo-700"
                        : " hover:text-gray-600 text-gray-800 hover:border-gray-200 border border-white border-dotted"
                ]}"
            >
                { a.text }
            </a>
        {/each}
    {/if}
</nav>