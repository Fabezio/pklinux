<script>
  import Bar from "../components/UI/Bar.svelte";
  import { distros } from "../store/distros";
</script>

<style>
  h3 {
    margin-top: 2rem;
  }

  a {
    width: 50%;
  }
</style>

<h1>Distributions</h1>
<h2>Avant de commencer</h2>
<p>
  Le choix d'une distribution Linux dépend de ce que vous en attendez. Comme dit
  précédemment, si vous voulez faire de la MAO ou du développement informatique,
  il vaudra mieux s'écarter de la distro basique comme Ubuntu ou Manjaro.
  Quoique la possibilité d'installer les outils nécessaires à cette fin n'est
  pas à exclure. Dans tous les cas je vous suggère d'apprendre quelques notions
  de terminal (l'interface de ligne de commande - CLI). Ca va plus vite
  d'installer toute une pléiade de paquets à la volée en une seule commande que
  cliquer sur plein de boutons en interface graphique. Donc le terminal est
  incontournable pour ne pas dire nécessaire. De plus vous pourrez contrôler
  votre PC, automatiser les tâches les plus chronophages, ajouter des
  raccourcis, des alias pour vos commandes, des plus simples aux plus complexes.
  Bien sûr ce n'est pas obligatoire, juste plus confortable. Avec le temps (pas
  beaucoup) et de la pratique (un peu plus) vous vous habituerez et vous
  demanderez pourquoi vous ne vous y êtes pas mis plus tôt. Avant de vous
  lancer, je ne saurais trop vous recommander de prendre
  <a href="advices">quelques dispositions</a>
  afin de bien préparer le terrain.
</p>
<h2>La liste</h2>
<p>
  Passons au plat de résistance, la liste tant attendue. Non exhaustive, elle
  vous permettra de faire votre choix
</p>
<h3>Pour débuter</h3>
<div class="">
  {#each distros.debutant as distro}
    <Bar {distro} />
  {/each}
</div>

<h3>Une fois à l'aise</h3>
<p>
  Vous souvenez-vous quand je vous avais dit qu'il était possible de remplacer
  une distribution? Vous avez mainetenat l'occasion de le mettre en pratique.
  J'espère tout de même que vous avez bien suivi les
  <a href="advices">conseils</a>
  que je vous avais prodigués. Sinon une sauvegarde sera vraiment obligatoire,
  sous peine de perdre tout ce que vous avez fait jusque là.
</p>
{#each distros.confirme as distro}
  <Bar {distro} />
{/each}

<h3>Pour les avertis</h3>
<p>
  Certaines distributions s'installent
  <q>à la main</q>, si vous êtes un administrateur système, cette contrainte
  devrait être une formalité.
</p>
{#each distros.averti as distro}
  <Bar {distro} />
{/each}
