<script lang="ts">
    import Navbarlink from "./navigation/navbarlink.svelte";

  export let links;
</script>

<nav>
  {#each links as { href, label }}
    <Navbarlink link={href} label={label} />
  {/each}
</nav>

<style>
    nav {
      position : fixed;
      box-sizing: border-box;
      top : 20px;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 50px;
      z-index: 50;
      width: fit-content;
      padding: 10px 50px;
      background: var(--color-normal);
      backdrop-filter: blur(30px);
      border-radius: 20px;
      border: 2px solid var(--border-color-normal);
      box-shadow: 0 8px 24px var(--box-shadow-color);
    }
</style>
