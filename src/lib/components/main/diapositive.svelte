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
        z-index: 0;
    }

    div > :global(*:not(canvas):not(footer)) {
        position: relative;
        z-index: 1;
    }

    div > :global(footer) {
        z-index: 10;
    }

    h1 {
        font-size: 3rem;
        text-align: center;
    }
</style>