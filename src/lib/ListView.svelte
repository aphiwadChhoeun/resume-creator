<script>
    export let title = "Title";
    export let data = [];
</script>

<div class="my-4">
    <div class="flex flex-row">
        <slot name="icon" />

        <h3 class="text-lg">{title}</h3>
    </div>
    <div class="flex flex-col">
        {#each data as item}
            <slot {item} />
        {/each}
    </div>
</div>
