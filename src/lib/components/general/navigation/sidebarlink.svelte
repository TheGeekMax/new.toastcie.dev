<script lang="ts">
    import { House } from '@lucide/svelte';
    let { children, link = "", label = "", selected = false, onclick = () => {} } = $props();
</script>

<a 
    href={link} 
    on:click|preventDefault={onclick} 
    class:selected
>
    {#if children}
        {@render children()}
    {:else}
        <House size={20} strokeWidth={2} />
    {/if}
    <span>{label}</span>
</a>

<style>
    a {
        display: flex;
        align-items: center;
        gap: 12px;
        box-sizing: border-box;
        font-size: 14px;
        font-weight: 700;
        text-transform: uppercase;
        text-decoration: none;
        color: rgba(255, 255, 255, 0.7);
        width: 200px;
        max-width: 380px;
        padding: 16px 24px;
        background: rgba(60, 60, 80, 0.4);
        backdrop-filter: blur(20px);
        border-radius: 50px;
        border: 2px solid rgba(255, 255, 255, 0.1);
        box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
        margin: 10px 0;
        transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        cursor: pointer;
    }

    a:hover {
        color: rgba(100, 150, 255, 1);
        border-color: rgba(100, 150, 255, 0.4);
        background: rgba(70, 70, 90, 0.5);
        transform: translateX(30px);
        box-shadow: 0 6px 30px rgba(100, 150, 255, 0.2);
    }

    a.selected {
        color: rgba(100, 150, 255, 1);
        border-color: rgba(100, 150, 255, 0.6);
        background: rgba(80, 80, 100, 0.6);
        transform: translateX(30px);
        box-shadow: 0 8px 35px rgba(100, 150, 255, 0.3);
    }

    a :global(svg) {
        flex-shrink: 0;
        transition: transform 0.3s ease;
    }

    a:hover :global(svg),
    a.selected :global(svg) {
        transform: scale(1.1);
    }

    span {
        flex: 1;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
    }
</style>