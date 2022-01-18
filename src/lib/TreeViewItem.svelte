<script>
    export let item = {};
</script>

<div class="treeview flex flex-row odd:text-right even:justify-end">
    <div class="basis-1/2 relative">
        <div class="font-semibold">
            {item.title}
        </div>

        {#if item.sub_title}
            <div>
                <span>{item.sub_title}</span>
                {#if item.type}
                    - <span>{item.type}</span>
                {/if}

                {#if item.gpa}
                    - <span>GPA: {item.gpa}</span>
                {/if}
            </div>
        {/if}

        {#if item.duration}
            <div class="text-slate-400">
                {item.duration}
            </div>
        {/if}

        {#if item.location}
            <div class="text-slate-400">
                {item.location}
            </div>
        {/if}

        {#if item.description}
            <div>
                {item.description}
            </div>
        {/if}
    </div>
</div>

<style>
    :root {
        --bullet-size: 20px;
    }

    div.treeview:nth-child(odd) > div {
        @apply pr-6;
    }

    div.treeview:nth-child(odd) > div::before {
        content: "";
        position: absolute;
        top: 0;
        right: -2px;
        height: 100%;
        @apply border-r-4;
    }

    div.treeview:nth-child(odd) > div::after {
        content: "";
        position: absolute;
        right: calc(calc(var(--bullet-size) / 2) * -1);
        width: var(--bullet-size);
        height: var(--bullet-size);
        transform: translateY(-50%);
        @apply bg-slate-400 rounded-full top-1/2;
    }

    div.treeview:nth-child(even) > div {
        @apply pl-6;
    }

    div.treeview:nth-child(even) > div::before {
        content: "";
        position: absolute;
        left: -2px;
        height: 100%;
        @apply border-l-4 top-0;
    }

    div.treeview:nth-child(even) > div::after {
        content: "";
        position: absolute;
        left: calc(calc(var(--bullet-size) / 2) * -1);
        width: var(--bullet-size);
        height: var(--bullet-size);
        transform: translateY(-50%);
        @apply bg-slate-400 rounded-full top-1/2;
    }
</style>
