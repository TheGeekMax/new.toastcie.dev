<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import Navbar from '$lib/components/general/navbar.svelte';
	import links from '$lib/ressources/general/navlinks.json';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>Toastcie.dev</title>
	<link rel="stylesheet" href="/style/vars.css" />
</svelte:head>


{@render children()}
<Navbar {links} />
