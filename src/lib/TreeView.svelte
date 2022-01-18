<script>
    export let title = "Title";
    export let data = [];
</script>

<div class="my-2">
    <h3 class="text-lg font-bold">{title}</h3>
    <div class="treeview flex flex-col">
        {#each data as item}
            <slot {item} />
        {/each}
    </div>
</div>
