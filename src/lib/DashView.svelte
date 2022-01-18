<script>
    export let title = "Title";
    export let data = [];
</script>

<div class="my-2">
    <h3 class="text-lg font-bold">{title}</h3>
    <div class="grid md:grid-cols-5 gap-2">
        {#each data as value}
            <div
                class="p-2 md:aspect-square sm:aspect-auto odd:bg-stone-200 even:bg-zinc-200 hover:bg-gray-400 transition-all dark:odd:bg-stone-700 dark:even:bg-zinc-700 dark:hover:bg-gray-600"
            >
                {value}
            </div>
        {/each}
    </div>
</div>
