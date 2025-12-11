<script>
    import Navbar from '$lib/components/general/navbar.svelte';
    import Toastfooter from "$lib/components/general/toastfooter.svelte";
    import Diapositive from "$lib/components/main/diapositive.svelte";

    import links from '$lib/ressources/general/navlinks.json';
</script>

<Navbar {links} />
<Diapositive style="background-color: lightcoral;">
    <h1>Page A</h1>
</Diapositive>
<Diapositive style="background-color: lightseagreen;">
    <h1>Page B</h1>
</Diapositive>
<Diapositive style="background-color: lightgoldenrodyellow;">
    <h1>Page C</h1>
    <Toastfooter />
</Diapositive>

<style>
    :global(html, body) {
        margin: 0;
        padding: 0;
        width: 100%;
        height: 100%;
        font-family: Arial, sans-serif;
    }
</style>