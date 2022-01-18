<script>
    export let contacts = {};

    const parsePhone = (str) => {
        return str.replaceAll(/[()-\s]/gi, "");
    };
</script>

<div class="my-4 flex flex-row gap-4 flex-wrap">
    {#if contacts.phone}
        <div>
            <span>
                <svg
                    class="w-6 h-6 inline-block"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                    xmlns="http://www.w3.org/2000/svg"
                    ><path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"
                    /></svg
                >
            </span>
            <span class="italic"
                ><a href="tel:{parsePhone(contacts.phone)}">{contacts.phone}</a
                ></span
            >
        </div>
    {/if}

    {#if contacts.email}
        <div>
            <span>
                <svg
                    class="w-6 h-6 inline-block"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                    xmlns="http://www.w3.org/2000/svg"
                    ><path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M16 12a4 4 0 10-8 0 4 4 0 008 0zm0 0v1.5a2.5 2.5 0 005 0V12a9 9 0 10-9 9m4.5-1.206a8.959 8.959 0 01-4.5 1.207"
                    /></svg
                >
            </span>
            <span class="italic"
                ><a href="mailto:{contacts.email}">{contacts.email}</a></span
            >
        </div>
    {/if}

    {#if contacts.linkedin}
        <div>
            <span>
                <svg
                    class="w-6 h-6 inline-block"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                    xmlns="http://www.w3.org/2000/svg"
                    ><path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M13.828 10.172a4 4 0 00-5.656 0l-4 4a4 4 0 105.656 5.656l1.102-1.101m-.758-4.899a4 4 0 005.656 0l4-4a4 4 0 00-5.656-5.656l-1.1 1.1"
                    /></svg
                >
            </span>
            <span class="italic"
                ><a href={contacts.linkedin} target="_blank"
                    >{contacts.linkedin}</a
                ></span
            >
        </div>
    {/if}
</div>
