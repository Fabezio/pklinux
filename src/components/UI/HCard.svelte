<script>
  export let card = {};
</script>

<style>
  .frame {
    width: 300px;
    height: 300px;
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
    max-width: 300px;
    max-height: 300px;
    /* vertical-align: middle; */
  }
  .card-footer > div {
    height: 3rem;
    /* background */
  }
</style>

<div class="card w-100">
  <div class="frame bg-white-50 m-2 mx-auto" >
    <!-- <div style="background-image: url({'images/tux/'+card.image || 'logo-512.png'}; background-size: cover; background-repeat: no-repeat;">

    </div> -->
    <img class="card-top-img" src={'images/tux/'+card.image || 'logo-512.png'} alt={card.name} />
  </div>

  <div class="card-footer">
    <div>
      <p>
        <!-- {card.name}
          <br> -->
          {card.desc}</p>
          
        </div>
  </div>
</div>
