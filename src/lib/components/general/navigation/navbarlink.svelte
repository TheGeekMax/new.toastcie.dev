<script lang="ts">
    export let link:string;
    export let label:string;
</script>

<a class="navbar-link" href={link} >{label}</a>

<style>
    a {
      position: relative;
      font-size: 0.875rem;
      font-weight: 600;
      letter-spacing: 0.025em;
      text-transform: uppercase;
      text-decoration: none;
      color: rgba(232, 232, 232, 0.9);
      padding: 0.5rem 1rem;
      border-radius: 8px;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    a::before {
      content: '';
      position: absolute;
      bottom: 0.35rem;
      left: 1rem;
      right: 1rem;
      height: 2px;
      background: linear-gradient(90deg, var(--color-primary), #6a9fff);
      transform: scaleX(0);
      transform-origin: right;
      transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      border-radius: 2px;
    }

    a:hover {
      color: #ffffff;
      background: rgba(74, 127, 255, 0.1);
      transform: translateY(-1px);
    }

    a:hover::before {
      transform: scaleX(1);
      transform-origin: left;
    }

    a:active {
      transform: translateY(0);
    }

    :global(nav:has(a.navbar-link:hover) a.navbar-link:not(:hover)) {
      color: rgba(160, 160, 160, 0.5);
    }

    @media (max-width: 768px) {
      a {
        font-size: 0.8125rem;
        padding: 0.4rem 0.75rem;
      }
    }
</style>