<script lang="ts">
    import { 
        Code2, FileJson, Coffee, Smartphone, Hash, Hexagon,
        Atom, Database, Zap, FileCode, Moon, Terminal,
        Circle, Palette, Brain, Triangle, Apple, Container, Ship
    } from '@lucide/svelte';
    import SkillCard from './skillcard.svelte';
</script>

<section id="competences" class="competences-section">
    <h2>Compétences</h2>
    
    <div class="skills-grid">
        <SkillCard icon={Code2} label="Python" description="Maîtrise niveau expert" cellWidth={2} />
        <SkillCard icon={FileJson} label="JavaScript" description="Développement frontend & backend" cellWidth={1} />
        <SkillCard icon={Atom} label="React.js" description="Bibliothèque UI" cellWidth={2} />
        <SkillCard icon={Database} label="SQL" description="Base de données" cellWidth={1} />
        <SkillCard icon={Zap} label="C++" description="Programmation système" cellWidth={1} />
        <SkillCard icon={Circle} label="Node.js" description="Développement backend" cellWidth={2} />
        <SkillCard icon={Triangle} label="Next.js" description="Framework React" cellWidth={1} />
        <SkillCard icon={Coffee} label="Java" description="Applications d'entreprise" cellWidth={2} />
        <SkillCard icon={Smartphone} label="Kotlin" description="Développement Android" cellWidth={2} />
        <SkillCard icon={Hash} label="C#" description="Développement .NET" cellWidth={2} />
        <SkillCard icon={Apple} label="Swift" description="Développement iOS" cellWidth={1} />
        <SkillCard icon={Container} label="Docker" description="Conteneurisation" cellWidth={1} />
        <SkillCard icon={Ship} label="Kubernetes" description="Orchestration de conteneurs" cellWidth={1} />
        <SkillCard icon={FileCode} label="Caml" description="Programmation fonctionnelle" cellWidth={1} />
        <SkillCard icon={Moon} label="Lua" description="Langage de script" cellWidth={1} />
        <SkillCard icon={Terminal} label="Bash" description="Script shell" cellWidth={1} />
        <SkillCard icon={Hexagon} label="F#" description="Programmation fonctionnelle" cellWidth={2} />
    </div>
</section>

<style>
    .competences-section {
        width: 100%;
        padding: 4rem 2rem;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    h2 {
        text-align: center;
        color: #fff;
        font-size: 2.5rem;
        margin-bottom: 3rem;
        font-weight: 700;
    }

    .skills-grid {
        display: grid;
        grid-template-columns: repeat(6, 1fr);
        gap: 1rem;
        max-width: 1000px;
        width: 100%;
    }

    @media (max-width: 768px) {
        .competences-section {
            padding: 3rem 1rem;
        }

        h2 {
            font-size: 2rem;
        }

        .skills-grid {
            grid-template-columns: 1fr;
            gap: 1rem;
        }

        .skill-card.large,
        .skill-card.medium {
            grid-column: span 1;
            min-height: 120px;
        }
    }
</style>