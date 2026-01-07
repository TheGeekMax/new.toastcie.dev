<script lang="ts">
    import { 
        Code2, FileJson, Coffee, Smartphone, Hash, Hexagon,
        Atom, Database, Zap, FileCode, Moon, Terminal,
        Circle, Palette, Brain, Triangle, Apple, Container, Ship
    } from '@lucide/svelte';

    import type { Component } from 'svelte';

    const skillsRow1: Array<{ name: string; description: string; icon: Component }> = [
        { name: 'Python', description: 'Maîtrise niveau expert', icon: Code2 },
        { name: 'JavaScript', description: 'Développement frontend & backend', icon: FileJson },
        { name: 'Java', description: 'Applications d\'entreprise', icon: Coffee },
        { name: 'Kotlin', description: 'Développement Android', icon: Smartphone },
        { name: 'C#', description: 'Développement .NET', icon: Hash },
        { name: 'F#', description: 'Programmation fonctionnelle', icon: Hexagon },
    ];

    const skillsRow2: Array<{ name: string; description: string; icon: Component }> = [
        { name: 'React.js', description: 'Bibliothèque UI', icon: Atom },
        { name: 'SQL', description: 'Base de données', icon: Database },
        { name: 'C++', description: 'Programmation système', icon: Zap },
        { name: 'Caml', description: 'Programmation fonctionnelle', icon: FileCode },
        { name: 'Lua', description: 'Langage de script', icon: Moon },
        { name: 'Bash', description: 'Script shell', icon: Terminal },
    ];

    const skillsRow3: Array<{ name: string; description: string; icon: Component }> = [
        { name: 'Node.js', description: 'Développement backend', icon: Circle },
        { name: 'UI/UX Design', description: 'Conception d\'interface & prototypage', icon: Palette },
        { name: 'AI & Machine Learning', description: 'Développement & déploiement de modèles', icon: Brain },
        { name: 'Next.js', description: 'Framework React', icon: Triangle },
        { name: 'Swift', description: 'Développement iOS', icon: Apple },
        { name: 'Docker', description: 'Conteneurisation', icon: Container },
        { name: 'Kubernetes', description: 'Orchestration de conteneurs', icon: Ship },
    ];
</script>

<section id="competences" class="competences-section">
    <h2>Compétences</h2>
    
    <div class="skills-container">
        <!-- Row 1: Left to Right -->
        <div class="skills-row">
            <div class="skills-track animate-ltr">
                {#each [...skillsRow1, ...skillsRow1] as skill}
                    <div class="skill-card">
                        <div class="skill-icon">
                            <svelte:component this={skill.icon} size={32} strokeWidth={1.5} />
                        </div>
                        <h3>{skill.name}</h3>
                        <p>{skill.description}</p>
                    </div>
                {/each}
            </div>
        </div>

        <!-- Row 2: Right to Left -->
        <div class="skills-row">
            <div class="skills-track animate-rtl">
                {#each [...skillsRow2, ...skillsRow2] as skill}
                    <div class="skill-card">
                        <div class="skill-icon">
                            <svelte:component this={skill.icon} size={32} strokeWidth={1.5} />
                        </div>
                        <h3>{skill.name}</h3>
                        <p>{skill.description}</p>
                    </div>
                {/each}
            </div>
        </div>

        <!-- Row 3: Left to Right -->
        <div class="skills-row">
            <div class="skills-track animate-ltr">
                {#each [...skillsRow3, ...skillsRow3] as skill}
                    <div class="skill-card">
                        <div class="skill-icon">
                            <svelte:component this={skill.icon} size={32} strokeWidth={1.5} />
                        </div>
                        <h3>{skill.name}</h3>
                        <p>{skill.description}</p>
                    </div>
                {/each}
            </div>
        </div>
    </div>
</section>

<style>
    .competences-section {
        width: 100%;
        padding: 4rem 2rem;
        overflow: hidden;
    }

    h2 {
        text-align: center;
        color: #fff;
        font-size: 2.5rem;
        margin-bottom: 1rem;
        font-weight: 700;
    }

    .skills-container {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }

    .skills-row {
        width: 100%;
        overflow: visible;
        position: relative;
        mask-image: linear-gradient(
            to right,
            transparent,
            black 10%,
            black 90%,
            transparent
        );
        padding: 10px 0;
    }

    .skills-track {
        display: flex;
        gap: 1.5rem;
        width: fit-content;
    }

    .animate-ltr {
        animation: scroll-ltr 30s linear infinite;
    }

    .animate-rtl {
        animation: scroll-rtl 30s linear infinite;
    }

    .skill-card:hover {
        animation-play-state: running;
    }

    @keyframes scroll-ltr {
        0% {
            transform: translateX(0);
        }
        100% {
            transform: translateX(-50%);
        }
    }

    @keyframes scroll-rtl {
        0% {
            transform: translateX(-50%);
        }
        100% {
            transform: translateX(0);
        }
    }

    .skill-card {
        min-width: 280px;
        height: 110px;
        background: rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(10px);
        border-radius: 16px;
        padding: 1rem;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;
        border: 1px solid rgba(255, 255, 255, 0.2);
        transition: all 0.3s ease;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        position: relative;
        will-change: transform;
    }

    .skill-card:hover {
        transform: translateY(-5px) translateZ(0);
        background: rgba(255, 255, 255, 0.15);
        border-color: rgba(255, 255, 255, 0.4);
        box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
    }

    .skill-icon {
        font-size: 2rem;
        margin-bottom: 0.5rem;
    }

    .skill-card h3 {
        color: #fff;
        font-size: 1.25rem;
        font-weight: 600;
        margin: 0 0 0.5rem 0;
    }

    .skill-card p {
        color: rgba(255, 255, 255, 0.7);
        font-size: 0.9rem;
        margin: 0;
        line-height: 1.4;
    }

    @media (max-width: 768px) {
        .competences-section {
            padding: 3rem 1rem;
        }

        h2 {
            font-size: 2rem;
        }

        .skill-card {
            min-width: 240px;
            height: 100px;
        }

        .skills-container {
            gap: 1.5rem;
        }
    }
</style>
