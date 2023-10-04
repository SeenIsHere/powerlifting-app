<script lang="ts">
    export let name: string;
</script>

<div class="program" style="background: rgb({Math.floor(Math.random() * 255)}, {Math.floor(Math.random() * 255)}, {Math.floor(Math.random() * 255)})">
{name}
</div>


<style lang="scss">
    .program {
        width: 90%;
        height: 10vh;
    }
</style>