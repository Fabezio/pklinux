<script>
  export let theme;
</script>

<style>
  div {
    display: block;
    width: 100%;
    position: relative;
    bottom: 0;
    height: 3rem;
  }
  footer {
    position: fixed;
    bottom: 0;
  }
</style>

<div />
<footer
  class="bg-{theme.bg} text-{theme.color} w-100 border-top text-center py-3">
  pklinux &copy;
  {new Date().getFullYear()}
</footer>
