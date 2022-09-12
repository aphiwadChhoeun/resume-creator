<script>
    export let item = {};
</script>

<div class="my-2 flex flex-col pl-4 border-l-4">
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

    {#if item.link}
        <div>
            <a href={item.link} target="_blank" rel="noopener">Show Credential</a>
        </div>
    {/if}
</div>
