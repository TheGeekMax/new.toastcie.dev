<script lang="ts">
    let { children, selected = 0 } = $props();
    
    let arrowTop = $state(0);
    let asideElement: HTMLElement | null = null;
    
    $effect(() => {
        if (asideElement) {
            const links = asideElement.querySelectorAll('a');
            if (links[selected]) {
                const linkRect = links[selected].getBoundingClientRect();
                arrowTop = linkRect.top + (linkRect.height / 2) - 16;
            }
        }
    });
</script>


<aside bind:this={asideElement}>
	{@render children()}
</aside>

<div class="scroll-arrow" style="top: {arrowTop}px">
    ▶
</div>

<style>
    aside {
        position: fixed;
        top: 50px;
        left: 10px;
        width: 420px;
        height: calc(100% - 20px);
        z-index: 10;
        padding: 20px;
        box-sizing: border-box;
        overflow-y: auto;
        overflow-x: visible;
    }
    
    .scroll-arrow {
        position: fixed;
        left: 20px;
        font-size: 32px;
        color: #4a7fff;
        text-shadow: 0 0 20px #4a7fff, 0 0 40px #4a7fff;
        transition: top 0.2s ease-out;
        z-index: 1000;
        pointer-events: none;
    }
</style>
