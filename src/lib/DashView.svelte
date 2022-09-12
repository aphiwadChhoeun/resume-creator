<script>
    export let title = "Title";
    export let data = [];
</script>

<div class="my-4">
    <h3 class="text-lg">{title}</h3>
    <div class="flex flex-row flex-wrap gap-1 print:flex">
        {#each data as value}
            <div
                class="p-2 rounded bg-gradient-to-br from-blue-200 to-cyan-200 text-neutral-900"
            >
                {value}
            </div>
        {/each}
    </div>
</div>
