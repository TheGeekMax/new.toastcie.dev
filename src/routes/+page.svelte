<script>
    import Navbar from '$lib/components/navbar.svelte';
    import Toastfooter from "$lib/components/general/toastfooter.svelte";
    import Diapositive from "$lib/components/main/diapositive.svelte";

    const links = [
        { href: '#', label: 'Link 1', color: '#fff', hoverColor: '#ff7a18' },
        { href: '#', label: 'Link 2', color: '#fff', hoverColor: '#ff7a18' },
        { href: '#', label: 'Link 3', color: '#fff', hoverColor: '#ff7a18' },
        { href: '#', label: 'Link 4', color: '#fff', hoverColor: '#ff7a18' },
        { href: '#', label: 'Link 5', color: '#fff', hoverColor: '#ff7a18' }
    ];
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