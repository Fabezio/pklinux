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
    filter: opacity(0.75);
  }
  .frame:hover {
    filter: opacity(0.95);
  }

  img {
    max-width: 300px;
    max-height: 300px;
  }
  .card-footer > div {
    height: 3rem;
  }
</style>

<div class="card rounded ">
  <div class="frame m-2 mx-auto">
    <img
      class="card-top-img"
      src={'images/tux/' + card.image || 'logo-512.png'}
      alt={card.name} />
  </div>

  <div class="card-footer">
    <div>
      <p>{card.desc}</p>
    </div>
  </div>
</div>
