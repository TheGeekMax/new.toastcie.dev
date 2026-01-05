<script lang="ts">
    import { onMount } from 'svelte';
    
    export let topColor: string = '#000';
    export let bottomColor: string = '#000';

    let canvas: HTMLCanvasElement;
    let animationId: number;

    interface Star {
        x: number;
        y: number;
        size: number;
        color: string;
        xvelocity: number;
        yvelocity: number;
    }

    const generateColor = (): string => {
        const lerp = (a: number, b: number, t: number): number => a + (b - a) * t;
        const t = Math.random();
        const r = Math.round(lerp(230, 230, t));
        const g = Math.round(lerp(229, 217, t));
        const b = Math.round(lerp(207, 207, t));
        return `rgb(${r}, ${g}, ${b})`;
    };

    onMount(() => {
        if (!canvas) return;

        const ctx = canvas.getContext('2d');
        if (!ctx) return;

        canvas.width = canvas.offsetWidth;
        canvas.height = canvas.offsetHeight;

        const stars: Star[] = [];
        const starCount = 250;
        const speed = 0.125;

        for (let i = 0; i < starCount; i++) {
            stars.push({
                x: Math.random() * canvas.width,
                y: Math.random() * canvas.height,
                size: Math.random() * 2 + 0.5,
                color: generateColor(),
                xvelocity: Math.random() * speed * 2 - speed,
                yvelocity: Math.random() * speed * 2 - speed,
            });
        }

        const animate = () => {
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            stars.forEach((star) => {
                ctx.beginPath();
                ctx.arc(star.x, star.y, star.size, 0, 2 * Math.PI);
                ctx.fillStyle = star.color;
                ctx.fill();

                star.x += star.xvelocity;
                star.y += star.yvelocity;

                if (star.x > canvas.width) star.x = 0;
                if (star.x < 0) star.x = canvas.width;
                if (star.y > canvas.height) star.y = 0;
                if (star.y < 0) star.y = canvas.height;
            });

            animationId = requestAnimationFrame(animate);
        };

        animate();

        return () => cancelAnimationFrame(animationId);
    });
</script>

<style>
    canvas{
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 0;
    }
</style>

<canvas
    bind:this={canvas}
    style:background="linear-gradient(to bottom, {topColor}, {bottomColor})"
>
</canvas>
