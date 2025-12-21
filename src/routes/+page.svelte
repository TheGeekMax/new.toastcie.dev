<script lang="ts">
    import Sidebar from '$lib/components/general/sidebar.svelte';
    import Home from '$lib/components/main/home.svelte';
    import Toastfooter from "$lib/components/general/toastfooter.svelte";
    import Diapositive from "$lib/components/main/diapositive.svelte";
    import Sky from '$lib/components/main/sky.svelte';
    import Sidebarlink from '$lib/components/general/navigation/sidebarlink.svelte';
    import { onMount } from 'svelte';
    import { House, CircleUser, BookmarkCheck, FolderClosed, Contact, Rocket } from '@lucide/svelte';

    const Sections = {
        HOME: 0,
        ABOUT: 1,
        JOURNEY: 2,
        SKILLS: 3,
        PROJECTS: 4,
        CONTACT: 5
    } as const;

    let selected : number = Sections.HOME;

    function handleClick(section: number) {
        const diapoElements = document.getElementsByClassName('diapo-container');
        if (diapoElements.length > section) {
            const targetDiapo = diapoElements[section] as HTMLElement;
            targetDiapo.scrollIntoView({ behavior: 'smooth' });
            selected = section;
        }
    }

    onMount(() => {
        const observer = new IntersectionObserver(
            (entries) => {
                entries.forEach((entry) => {
                    if (entry.isIntersecting) {
                        const diapoElements = Array.from(document.getElementsByClassName('diapo-container'));
                        const index = diapoElements.indexOf(entry.target as HTMLElement);
                        if (index !== -1) {
                            selected = index;
                        }
                    }
                });
            },
            {
                threshold: 0.5 // Trigger when 50% of the element is visible
            }
        );

        const diapoElements = document.getElementsByClassName('diapo-container');
        Array.from(diapoElements).forEach((element) => {
            observer.observe(element);
        });

        return () => {
            observer.disconnect();
        };
    });
</script>

<Sidebar {selected}>
    <Sidebarlink
        label="Home"
        link="/"
        onclick={() => handleClick(Sections.HOME)} 
        selected={selected === Sections.HOME}
    ><House size={20} strokeWidth={2}/></Sidebarlink>
        <Sidebarlink
        label="Qui suis-je"
        link="/"
        onclick={() => handleClick(Sections.ABOUT)} 
        selected={selected === Sections.ABOUT}
    ><CircleUser size={20} strokeWidth={2}/></Sidebarlink>
    <Sidebarlink
        label="Mon parcours"
        link="/"
        onclick={() => handleClick(Sections.JOURNEY)} 
        selected={selected === Sections.JOURNEY}
    ><Rocket size={20} strokeWidth={2}/></Sidebarlink>
    <Sidebarlink
        label="Competences"
        link="/"
        onclick={() => handleClick(Sections.SKILLS)} 
        selected={selected === Sections.SKILLS}
    ><BookmarkCheck size={20} strokeWidth={2}/></Sidebarlink>
    <Sidebarlink
        label="Projets"
        link="/"
        onclick={() => handleClick(Sections.PROJECTS)} 
        selected={selected === Sections.PROJECTS}
    ><FolderClosed size={20} strokeWidth={2}/></Sidebarlink>
    <Sidebarlink
        label="Me contacter"
        link="/"
        onclick={() => handleClick(Sections.CONTACT)} 
        selected={selected === Sections.CONTACT}
    ><Contact size={20} strokeWidth={2}/></Sidebarlink>
</Sidebar>

<Diapositive >
    <Sky topColor="var(--night-color-1)" bottomColor="var(--night-color-1)" />
    <Home/>
</Diapositive>
<Diapositive>
    <Sky topColor="var(--night-color-1)" bottomColor="var(--night-color-2)" />
    <h1>Qui suis-je</h1>
</Diapositive>
<Diapositive>
    <Sky topColor="var(--night-color-2)" bottomColor="var(--night-color-2)" />
    <h1>Mon parcours</h1>
</Diapositive>
<Diapositive>
    <Sky topColor="var(--night-color-2)" bottomColor="var(--night-color-3)" />
    <h1>Competences</h1>
</Diapositive>
<Diapositive>
    <Sky topColor="var(--night-color-3)" bottomColor="var(--night-color-4)" />
    <h1>Projet recents (3 derniers)</h1>
</Diapositive>
<Diapositive >
    <Sky topColor="var(--night-color-4)" bottomColor="var(--night-color-5)" />
    <h1>Me contacter</h1>
    <Toastfooter />
</Diapositive>


<style>
    :global(html, body) {
        margin: 0;
        padding: 0;
        width: 100%;
        height: 100%;
        overflow-x: hidden;
        font-family: Arial, sans-serif;
        color: var(--font-color);
        scrollbar-width: none; /* Firefox */
        -ms-overflow-style: none; /* IE and Edge */
    }

    :global(html::-webkit-scrollbar, body::-webkit-scrollbar) {
        display: none; /* Chrome, Safari, Opera */
    }

    :global(.diapo-container::-webkit-scrollbar) {
        display: none;
    }
</style>