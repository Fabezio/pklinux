<script>
  export let card = {};
</script>

<style>
  .frame {
    width: 10rem;
      
    max-height: 10rem;
    display: flex;
    align-items: center;
    justify-content: center;
    vertical-align: middle;
    /* clear: both; */
  }
  img {
    max-width: 10rem;
    max-height: 10rem;
    vertical-align: middle;
  }
</style>

<div class="card" style="width: 10rem;">
  <div class="frame">
    <img
      src={'images/tux/' + card.image || 'logo-512.png'}
      class="card-img-top bg-secondary"
      alt={card.name} />
  </div>
  <div class="card-body">
    <p class="card-text">{card.desc}</p>
  </div>
</div>

<!-- <figure class="my-3 mx-2 w-25">
  <div class="frame ">
    <img src={"images/tux/"+card.image || 'logo-512.png'} alt={card.name} />
  </div>

  <figcaption class="mt-2">
    <p>{card.name}
    <br>{card.desc}</p>
  </figcaption>
</figure> -->
