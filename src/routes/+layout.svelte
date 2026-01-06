<script lang="ts">
	import favicon from '/static/img/favicon.svg';
	import Navbar from '$lib/components/general/navbar.svelte';
	import links from '$lib/ressources/general/navlinks.json';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>Toastcie.dev</title>
	
	<meta name="description" content="Portfolio d'un développeur passionné. Découvrez mes projets, compétences et parcours dans le développement logiciel et DevOps." />
	<meta name="keywords" content="développeur, portfolio, dev, projets, DevOps, ingénieur informatique" />
	<meta name="author" content="Toastcie" />
	
	<!-- Open Graph / Facebook -->
	<meta property="og:type" content="website" />
	<meta property="og:title" content="Toastcie.dev - Portfolio" />
	<meta property="og:description" content="Portfolio d'un développeur passionné. Découvrez mes projets, compétences et parcours dans le développement logiciel et DevOps." />
	<meta property="og:image" content="/img/trauma.png" />
	
	<!-- Twitter -->
	<meta name="twitter:card" content="summary" />
	<meta name="twitter:title" content="Toastcie.dev - Portfolio" />
	<meta name="twitter:description" content="Portfolio d'un développeur passionné. Découvrez mes projets, compétences et parcours dans le développement logiciel et DevOps." />
	<meta name="twitter:image" content="/img/trauma.png" />
	
	<link rel="stylesheet" href="/style/vars.css" />
</svelte:head>


{@render children()}
<Navbar {links} />
