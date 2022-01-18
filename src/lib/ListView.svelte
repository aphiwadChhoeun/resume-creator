<script>
    export let title = "Title";
    export let data = [];
</script>

<div>
    <h3 class="text-lg font-bold">{title}</h3>
    <div class="flex flex-col">
        {#each data as item}
            <slot {item} />
        {/each}
    </div>
</div>
