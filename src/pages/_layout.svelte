<script>
  import Nav from './nav.svelte';
</script>

<Nav />
<div class="app">
  <slot />
</div>

<style>
  .app {
    width: 100%;
    display: flex;
    justify-content: center;
  }
</style>