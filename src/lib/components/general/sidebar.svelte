<script lang="ts">
    let { children, selected = 0 } = $props();
    
    // Sidebar top (50px) + padding (20px) + half of first link (~28px) = 98px base
    // Each link: 16px padding top + 16px padding bottom + 10px margin top + 10px margin bottom + ~20px content = 72px
    let arrowTop = $derived(94 + (selected * 65.5));
</script>


<aside>
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
