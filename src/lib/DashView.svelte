<script>
    export let title = "Title";
    export let data = [];
</script>

<div class="my-2">
    <h3 class="text-lg">{title}</h3>
    <div class="flex flex-row flex-wrap gap-1 print:flex">
        {#each data as value}
            <div
                class="p-2 rounded bg-gradient-to-r from-green-500 to-lime-500 text-neutral-900"
            >
                {value}
            </div>
        {/each}
    </div>
</div>
