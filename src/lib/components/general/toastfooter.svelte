<script lang="ts">
    let year = new Date().getFullYear();
</script>

<footer>
    @2025-{year} Toastcie.dev, All rights reserved.
</footer>

<style>
    footer {
        position: absolute;
        box-sizing: border-box;
        bottom: 20px;
        left: 50%;
        transform: translateX(-50%);
        text-align: center;
        font-size: 0.9rem;
        z-index: 50;
        width: fit-content;
        padding: 0.875rem 2.5rem;
        background: rgba(50, 50, 60, 0.75);
        backdrop-filter: blur(40px) saturate(180%);
        -webkit-backdrop-filter: blur(40px) saturate(180%);
        border-radius: 50px;
        border: 1px solid rgba(255, 255, 255, 0.08);
        box-shadow: 
            0 8px 32px rgba(0, 0, 0, 0.4),
            0 2px 8px rgba(0, 0, 0, 0.2),
            inset 0 1px 0 rgba(255, 255, 255, 0.05);
        transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    footer::before {
        content: '';
        position: absolute;
        inset: -1px;
        border-radius: 50px;
        padding: 1px;
        background: linear-gradient(135deg, 
            rgba(255, 255, 255, 0.1) 0%, 
            rgba(255, 255, 255, 0.02) 50%, 
            rgba(255, 255, 255, 0.05) 100%);
        -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
        -webkit-mask-composite: xor;
        mask-composite: exclude;
        pointer-events: none;
    }

    footer:hover {
        box-shadow: 
            0 12px 40px rgba(0, 0, 0, 0.5),
            0 4px 12px rgba(0, 0, 0, 0.3),
            inset 0 1px 0 rgba(255, 255, 255, 0.08);
        border-color: rgba(255, 255, 255, 0.12);
    }

    @media (max-width: 768px) {
        footer {
            padding: 0.75rem 1.5rem;
        }
    }
</style>