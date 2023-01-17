<script>
    export let list = [];
</script>

<nav class="inline-flex justify-end w-full">
    {#if list.length }
        {#each list as a, ind }
            <a 
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