<script lang="ts">
    import { onMount, createEventDispatcher } from "svelte";

    export let prompt: string;

    let modal: HTMLDialogElement | null;
    onMount(() => {
        modal = document.querySelector("dialog.text-prompt")
    })

    const dispatch = createEventDispatcher()
    
    let text: string;

    export const close = () => modal?.close()
    export const open = () => modal?.showModal()
    const submit = () => {
        close()
        dispatch("submit", text)
    }
</script>

<dialog class="text-prompt">
    <input on:change={(ev) => text = ev?.target?.value} name={prompt}/>

    <span>
        <button on:click={() => modal?.close()}>Close</button>
        <button on:click={submit}>Ok</button>
    </span>
</dialog>