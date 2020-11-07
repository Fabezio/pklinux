<script>
  export let card = {};
</script>

<style>
  .frame {
    width: 200px;
    height: 200px;
    display: flex;
    align-items: center;
    justify-content: center;
    /* vertical-align: middle; */
    
  }
  figure {
    /* display: block; */
    text-align: center;
  }
  img {
    max-width: 200px;
    max-height: 200px;
    /* vertical-align: middle; */
  }
</style>

<figure class="my-3 mx-2 w-25 ">
  <div class="frame ">
    <img src={card.image || 'logo-512.png'} alt={card.name} />
  </div>

  <figcaption class="mt-2 text-center">
    <p>
      <!-- {card.name}
    <br> -->
    {card.desc}</p>
  </figcaption>
</figure>
