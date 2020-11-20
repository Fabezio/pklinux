<script>
  import Nav from "../components/Nav.svelte";
  import Footer from "../components/Footer.svelte";
  const theme = {
    bg: "info",
    color: "light",
  };
  export let segment;
</script>

<style>
</style>

<Nav {segment} {theme} />

<main class="container my-5">
  <slot />
</main>

<Footer {theme} />
