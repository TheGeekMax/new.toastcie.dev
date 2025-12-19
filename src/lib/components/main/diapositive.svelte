<script lang="ts">
    let props = $props();
</script>

<div {...props} class="diapo-container">
    {@render props.children()}
</div>

<style>
    :global(html, body) {
        scroll-behavior: smooth;
        scroll-snap-type: y mandatory;
        overflow-x: hidden;
    }

    div{
        width: 100vw;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        scroll-snap-align: start;
        padding: 20px;
        box-sizing: border-box;
        position: relative;
    }

    h1 {
        font-size: 3rem;
        text-align: center;
    }
</style>