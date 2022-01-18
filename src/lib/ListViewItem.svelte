<script>
    export let item = {};
</script>

<div class="my-2 flex flex-row">
    <div class="pr-2">
        <svg
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
            ><path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z"
            /></svg
        >
    </div>

    <div>
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
