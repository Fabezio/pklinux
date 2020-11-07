<script>
  // import { each } from "svelte/internal";
  import Card from "../components/UI/Card.svelte";

  const thumbnails = [
    {
      name: "mascotte",
      desc: "Mascotte Linux",
      image: "tux original.png",
    },
    {
      name: "ami",
      desc: "linux est ton ami",
      image: "friend-tux.jpeg",
    },
    {
      name: "puissant",
      desc: "linux est plus puissant qu'il en a l'air",
      image: "vegeta tux.png",
    },
    {
      name: "adorable",
      desc: "Si un OS pouvait adorable, ce serait Linux",
      image: "female tux.png",
    },
    {
      name: "transparent",
      desc: "linux n'a rien à cacher, tout est accessible",
      image: "transparent tux.png",
    },
    {
      name: "vigilant",
      desc: "linux a le souci de votre sécurité",
      image: "viking tux.png",
    },
    {
      name: "attention",
      desc: "si linux dérape ça ne sera pas sa faute",
      image: "vader tux.png",
    },
  ];
</script>

<style>
  /* .flex {
    display: flex;
  } */
</style>

<h1>Vignettes</h1>
<!-- <div class="card-deck"> -->
<!-- <div class="flex justify-content-center"> -->
<div class="row">
  {#each thumbnails as thumbnail}
    <div class="col-lg-4 my-3">
      <Card card={thumbnail} />
      <!-- <figure>
      <img src={thumbnail.image} alt={thumbnail.name} />
      <figcaption>
        
        
        <p>{thumbnail.name}</p>
        <p>{thumbnail.desc}</p>
      </figcaption>
      
    </figure> -->
  </div>
    {/each}
</div>
