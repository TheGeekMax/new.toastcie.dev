<script>
  export let links = [];
</script>

<nav>
  {#each links as link}
    <a href={link.href} style="--base-color: {link.color}; --hover-color: {link.hoverColor}">{link.label}</a>
  {/each}
</nav>

<style>
        * {
    box-sizing: border-box;
    }

    body {
    font-family: system-ui;
    color: #fff;
    margin: 0;
    padding: 80px 30px;
    background-color: #030303;
    }

    nav {
    position : fixed;
    top : 10px;
    margin-left: auto;
    margin-right: auto;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 50px;
    }

    nav a {
    font-size: 18px;
    font-weight: 700;
    text-transform: uppercase;
    text-decoration: none;
    color: var(--base-color, #fff);
    padding: 0.4rem 0;
    transition: color 0.3s ease-in-out, opacity 0.3s ease-in-out;
    }

    nav a:hover {
    color: var(--hover-color, #ff7a18);
    }

    nav:has(a:hover) a:not(:hover) {
    opacity: 0.3;
    }
</style>
