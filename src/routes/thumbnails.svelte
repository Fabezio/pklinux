<script>
  // import { each } from "svelte/internal";
  import Card from '../components/UI/Card.svelte'

  const thumbnails = [
    {
      name: "mascotte",
      desc: "Mascotte Linux",
      image:
    
    "tux.jpeg"},
    {
      name: "ami",
      desc: "linux est ton ami",
      image:
        "friend-tux.jpeg",
    },
    {
      name: "puissant",
      desc: "linux est plus puissant qu'il en a l'air",
      image:
        "saiyan tux.jpeg",
    },
  ];
</script>

<style>
  /* .flex {
    display: flex;
  } */
</style>

<h1>Vignettes</h1>
<div class="card-deck">
<!-- <div class="flex justify-content-center"> -->
  {#each thumbnails as thumbnail}
    <Card card={thumbnail} />
    <!-- <figure>
    <img src={thumbnail.image} alt={thumbnail.name} />
    <figcaption>

      
      <p>{thumbnail.name}</p>
      <p>{thumbnail.desc}</p>
    </figcaption>
    
      </figure> -->
  {/each}
</div>
