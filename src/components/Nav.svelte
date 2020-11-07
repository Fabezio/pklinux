<script>
	import Clock from './UI/Clock.svelte'
  export let segment;
  const links = [
    { url: "distros", label: "distributions" },
    { url: "advices", label: "conseils" },
    { url: "environments", label: "Environnements" },
    { url: "thumbnails", label: "vignettes" },
  ];
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
    background-color: rgb(255, 62, 0);
    display: block;
    bottom: -1px;
  }

  a {
    text-decoration: none;
    padding: 1em 0.5em;
    display: block;
  }
</style>

<nav class="navbar navbar-expand-lg navbar-light bg-light sticky-top">
  <a class="navbar-brand" href=".">PKLINUX</a>
  <button
    class="navbar-toggler"
    type="button"
    data-toggle="collapse"
    data-target="#navbarSupportedContent"
    aria-controls="navbarSupportedContent"
    aria-expanded="false"
    aria-label="Toggle navigation">
    <span class="navbar-toggler-icon" />
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item">
        <a
          class="nav-link text-uppercase"
          aria-current={segment === undefined ? 'page' : undefined}
          href=".">accueil</a>
      </li>
      {#each links as link}
        <li class="nav-item">
          <a
            class="nav-link text-uppercase"
            aria-current={segment === link.url ? 'page' : undefined}
            href={link.url}>{link.label}</a>
        </li>
        <!-- <li><a aria-current="{segment === 'distros' ? 'page' : undefined}" href="distros">distributions</a></li>
		  <li><a aria-current="{segment === 'thumbnails' ? 'page' : undefined}" href="thumbnails">vignettes</a></li> -->
      {/each}
      <!-- <ul> -->

      <!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
				   the blog data when we hover over the link or tap it on a touchscreen -->
      <!-- <li><a rel=prefetch aria-current="{segment === 'blog' ? 'page' : undefined}" href="blog">blog</a></li> -->
      <!-- </ul> -->
      <!-- <li class="nav-item active">
        <a class="nav-link" href="#">Home
          <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item"><a class="nav-link" href="#">Link</a></li>
      <li class="nav-item dropdown">
        <a
          class="nav-link dropdown-toggle"
          href="#"
          id="navbarDropdown"
          role="button"
          data-toggle="dropdown"
          aria-haspopup="true"
          aria-expanded="false">
          Dropdown
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          <a class="dropdown-item" href="#">Action</a>
          <a class="dropdown-item" href="#">Another action</a>
          <div class="dropdown-divider" />
          <a class="dropdown-item" href="#">Something else here</a>
        </div>
      </li>
      <li class="nav-item">
        <a
          class="nav-link disabled"
          href="#"
          tabindex="-1"
          aria-disabled="true">Disabled</a>
      </li> -->
	</ul>
	<div>
		<Clock />
		<!-- horloge ici -->
	</div>
    <!-- <form class="form-inline my-2 my-lg-0">
      <input
        class="form-control mr-sm-2"
        type="search"
        placeholder="Search"
        aria-label="Search" />
      <button
        class="btn btn-outline-success my-2 my-sm-0"
        type="submit">Search</button>
    </form> -->
  </div>
</nav>
<nav />
