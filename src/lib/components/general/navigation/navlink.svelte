<script lang="ts">
    export let link:string;
    export let label:string;
    export let selected:boolean = false;
</script>

<a class="navbar-link" href={link} class:selected={selected}>{label}</a>

<style>
    a {
      font-size: 14px;
      font-weight: 700;
      text-transform: uppercase;
      text-decoration: none;
      color: var(--font-color);
      width:100%;
      padding: 0.4rem 0;
      transition: color 0.3s ease-in-out, opacity 0.3s ease-in-out;
    }

    a:hover {
      color: var(--color-primary);
    }

    .selected {
      color: var(--color-primary);
    }
</style>