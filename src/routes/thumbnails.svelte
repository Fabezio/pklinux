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
      desc: "Linux est ton ami",
      image: "friend-tux.jpeg",
    },
    {
      name: "puissant",
      desc: "Linux est plus puissant qu'il en a l'air",
      image: "vegeta tux.png",
    },
    {
      name: "adorable",
      desc: "Si un OS pouvait être adorable, ce serait Linux",
      image: "female tux.png",
    },
    {
      name: "transparent",
      desc: "Linux n'a rien à cacher, tout est accessible",
      image: "transparent tux.png",
    },
    {
      name: "vigilant",
      desc: "Linux a le souci de votre sécurité",
      image: "matrix.png",
    },
    {
      name: "attention",
      desc: "Si ça dérape, ça ne sera pas la faute de Linux",
      image: "vader tux.png",
    },
    {
      name: "flexibilité",
      desc: "Linux est aussi robuste que flexible",
      image: "luffy.png",
    },
    {
      name: "partenaire",
      desc: "GNU est partenaire de Linux",
      image: "gnu.png",
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
