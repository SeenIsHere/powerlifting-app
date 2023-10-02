<script lang="ts">


</script>

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

    .footbar {
        width: 100%;
        height: 10vh;
        background:red;
        position: absolute;
        bottom: 0;

        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }
</style>