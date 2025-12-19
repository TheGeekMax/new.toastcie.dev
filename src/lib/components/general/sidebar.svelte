<script lang="ts">
    let { children } = $props();
</script>


<aside>
	{@render children()}
</aside>

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
</style>
