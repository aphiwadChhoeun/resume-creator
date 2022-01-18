<script>
    export let theme = null;

    import { createEventDispatcher } from "svelte";
    let state = false;

    if (theme !== null) {
        state = theme;
    }

    const dispatch = createEventDispatcher();

    const onClicked = () => {
        state = !state;
        dispatch("changed", state);
    };
</script>

<svg
    class={`w-8 h-8 p-1 cursor-pointer inline-block ${
        state ? "bg-black stroke-gray-50" : "bg-neutral-300"
    } rounded-full`}
    viewBox="0 0 24 24"
    xmlns="http://www.w3.org/2000/svg"
    on:click={onClicked}
    ><path
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="2"
        d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"
    />
</svg>
