<script lang="ts">
    export let link:string;
    export let label:string;
</script>

<a class="navbar-link" href={link} >{label}</a>

<style>
    a {
      font-size: 14px;
      font-weight: 700;
      text-transform: uppercase;
      text-decoration: none;
      color: var(--font-color);
      padding: 0.4rem 0;
      transition: color 0.3s ease-in-out, opacity 0.3s ease-in-out;
    }

    a:hover {
      color: var(--color-primary);
    }

    :global(nav:has(a.navbar-link:hover) a.navbar-link:not(:hover)) {
      color: var(--color-disabled);
    }
</style>