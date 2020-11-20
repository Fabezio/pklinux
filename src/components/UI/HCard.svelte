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
  }

  img {
    max-width: 300px;
    max-height: 300px;
  }
  .card-footer > div {
    height: 3rem;
  }
</style>

<div class="card w-100">
  <div class="frame bg-white-50 m-2 mx-auto">
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
