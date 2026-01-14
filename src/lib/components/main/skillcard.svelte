<script lang="ts">
    import type { Component } from 'svelte';

    export let icon: Component;
    export let label: string;
    export let description: string;
    export let cellWidth: number = 1;
</script>

<div class="skill-card" style="grid-column: span {cellWidth};">
    <div class="skill-icon">
        <svelte:component this={icon} size={24} strokeWidth={1.5} />
    </div>
    <h3>{label}</h3>
    <p>{description}</p>
</div>

<style>
    .skill-card {
        background: rgba(255, 255, 255, 0.03);
        border: 1px solid rgba(255, 255, 255, 0.1);
        border-radius: 12px;
        padding: 1rem;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: flex-start;
        transition: all 0.3s ease;
        backdrop-filter: blur(10px);
        min-height: 100px;
    }

    .skill-card:hover {
        background: rgba(255, 255, 255, 0.05);
        border-color: rgba(150, 200, 255, 0.3);
        transform: translateY(-3px);
        box-shadow: 
            0 0 20px rgba(120, 180, 255, 0.2),
            0 5px 15px rgba(0, 0, 0, 0.3);
    }

    .skill-icon {
        color: #96c8ff;
        margin-bottom: 0.5rem;
        height: 24px;
        display: flex;
        align-items: center;
    }

    h3 {
        color: #ffffff;
        font-size: 1rem;
        font-weight: 600;
        margin: 0 0 0.25rem 0;
        height: 1.2em;
        display: flex;
        align-items: center;
        letter-spacing: 0;
    }

    p {
        color: #c4c0d0;
        font-size: 0.8rem;
        margin: 0;
        line-height: 1.3;
        font-weight: 300;
    }
</style>
