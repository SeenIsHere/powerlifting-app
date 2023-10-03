<script lang="ts">
import Program from "$lib/components/Program.svelte";
import TextPrompt from "$lib/components/TextPrompt.svelte";

let programs: Array<string> = []

function addPrograms(name: string){
    programs.push(name)
    programs = programs
}

let promptForProgramName;

</script>

<TextPrompt 
    bind:this={promptForProgramName} 
    prompt="Name" 
    on:submit={(ev) => addPrograms(ev.detail)}
/>

<div class="content">

    {#each programs as program}
        <Program name={program} /> 
    {/each}

    <div class="create-program">
        <button on:click={promptForProgramName.open}>Create New Program</button>
    </div>
</div>

<div class="footbar">
    <span>Home</span>
    <span>Progress</span>
    <span>Settings</span>
</div>

<style lang="scss">
    :global(html, body) {
        margin: 0;
        padding: 0;
    }

    .content {
        width: 100%;
        height: 90vh;
        position: absolute;
        top: 0;

        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .footbar {
        width: 100%;
        height: 10vh;
        background:grey;
        position: absolute;
        bottom: 0;

        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-evenly;
    }
</style>