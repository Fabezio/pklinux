<script>
  export let distro;
</script>

<style>
  hr {
    margin: 0;
    padding: 0;
    background: #333;

    border-radius: 50%;
    opacity: 0.5;
  }

  img {
    max-width: 100px;
    max-height: 100px;
  }

  button {
    width: 20%;
    background: purple;
    color: white;
    border-radius: 7px;
    padding: 1rem;
    border: 1px solid grey;
    font-weight: bold;
    font-size: 1.1rem;
    margin: 10px auto;
    display: block;
  }

  a {
    width: 50%;
  }
</style>

<div class="media border my-3 p-2 rounded-lg">
  <img
    class="align-self-start mr-3 rounded-lg"
    src={distro.logo}
    alt="logo {distro.name}" />

  <div class="media-body">
    <h5 class="mt-0">
      {#if distro.name.toLowerCase() == distro.family.toLowerCase() || !distro.name || !distro.family}
        <b>Distribution mère: {distro.family}</b>
      {:else}distribution: {distro.name} / <b>Famille: {distro.family}</b>{/if}
    </h5>
    <p>
      {@html distro.desc}
    </p>
    <hr />
    <button> <a href={distro.url}>{'visiter'.toUpperCase()}</a> </button>
  </div>
</div>
