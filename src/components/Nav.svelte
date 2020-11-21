<script>
  import Clock from "./UI/Clock.svelte";
  export let segment;
  export let theme;
  const links = [
    { url: "distros", label: "distributions" },
    { url: "advices", label: "conseils" },
    // { url: "environments", label: "Environnements" },
    { url: "terminal", label: "terminal" },
    { url: "thumbnails", label: "vignettes" },
  ];
  let open = false;
</script>

<style>
  nav {
    border-bottom: 1px solid rgba(255, 62, 0, 0.1);
    font-weight: 300;
    padding: 0 1em;
  }

  ul {
    margin: 0;
    padding: 0;
  }

  /* clearfix */
  ul::after {
    content: "";
    display: block;
    clear: both;
  }

  li {
    display: block;
    float: left;
  }

  [aria-current] {
    position: relative;
    display: inline-block;
  }

  [aria-current]::after {
    position: absolute;
    content: "";
    width: calc(100% - 1em);
    height: 2px;
    background-color: rgb(127, 255, 255);
    display: block;
    bottom: -7px;
  }

  a {
    text-decoration: none;
    padding: 1em 0.5em;
    display: block;
  }
</style>

<nav
  class="navbar navbar-expand-lg navbar-{theme.color == 'light' ? 'dark' : 'light'} bg-{theme.bg} sticky-top">
  <a class="navbar-brand" href=".">PKLINUX</a>
  <button
    on:click={() => {
      open = !open;
    }}
    class="navbar-toggler"
    type="button"
    data-toggle="collapse"
    data-target="#navbarSupportedContent"
    aria-controls="navbarSupportedContent"
    aria-expanded="false"
    aria-label="Toggle navigation">
    <span class="navbar-toggler-icon" />
  </button>

  <div
    class="collapse navbar-collapse {open ? 'show' : ''}"
    id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto text-center">
      <li class="nav-item">
        <a
          class="nav-link text-uppercase"
          aria-current={segment === undefined ? 'page' : undefined}
          href=".">accueil</a>
      </li>
      {#each links as link}
        <li class="nav-item {segment == link.url ? 'active' : ''}">
          <a
            class="nav-link text-uppercase"
            aria-current={segment === link.url ? 'page' : undefined}
            href={link.url}>{link.label}</a>
        </li>
      {/each}
    </ul>
    <div class="text-{theme.color} collapse {open ? '' : 'show'}">
      <Clock />
    </div>
  </div>
</nav>
<nav />
