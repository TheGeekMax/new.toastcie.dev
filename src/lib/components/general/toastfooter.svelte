<script lang="ts">
    let year = new Date().getFullYear();
</script>

<footer>
    @2025-{year} Toastcie.dev, All rights reserved.
</footer>

<style>

    footer {
        position: absolute;
        text-align: center;
        font-size: 0.9rem;
        bottom:15px;
        left: 0;
        right: 0;
        width: 100%;
        z-index: 10;
        padding: 12px 20px;
        display: inline-block;
        width: auto;
        max-width: calc(100% - 40px);
        left: 50%;
        right: auto;
        transform: translateX(-50%);
        box-sizing: border-box;
        overflow-y: auto;

        background: var(--color-normal);
        backdrop-filter: blur(30px);
        border-radius: var(--border-radius);
        border: 2px solid var(--border-color-normal);
        box-shadow: 0 8px 24px var(--box-shadow-color);
    }
</style>