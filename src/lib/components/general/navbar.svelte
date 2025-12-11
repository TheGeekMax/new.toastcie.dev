<script>
  export let links;
</script>

<nav>
  {#each links as link}
    <a href={link.href} >{link.label}</a>
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
      background: #fffc;
      backdrop-filter: blur(5px);
      border-radius: 20px;
      border: 3px solid #e0e0e0;
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.12);
    }

    nav a {
      font-size: 14px;
      font-weight: 700;
      text-transform: uppercase;
      text-decoration: none;
      color: #000;
      padding: 0.4rem 0;
      transition: color 0.3s ease-in-out, opacity 0.3s ease-in-out;
    }

    nav a:hover {
      color: #ff7a18;
    }

    nav:has(a:hover) a:not(:hover) {
      color: #5e5e63;
    }
</style>
