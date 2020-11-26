<script>
	// import { *assapper } from '@sapper/server';
  import Prompt from "../../components/Prompt.svelte";
  import PromptInput from "../../components/PromptInput.svelte";
  import Code from "../../components/Code.svelte";
  // import Uncalled from "../../components/terminal/Uncalled.svelte";
  let called = undefined;
  let answered = false;
  // function answeredUncalled() {
  //   called = false;
  //   answered = true;
  // }
  // function answeredCalled() {
  //   called = true;
  //   answered = true;
  // }
  let instruction
  // import Clock from "../components/UI/Clock.svelte";
</script>

<style>
  code {
    display: block;
    color: whitesmoke;
    background-color: darkslategray;
    padding: 8px;
    margin: 8px;
  }

  .item {
    width: 25rem !important;
  }
  i {
    font-weight: 600;
  }
  td {
    padding-right: 1rem;
  }
</style>

<svelte:head>
  <title>Terminal</title>
</svelte:head>
<h1>Terminal</h1>
<!-- {#if !answered}
  <p>Avez-vous ouvert un terminal?</p>
  <div class="btn-group">
    <button class="btn btn-success" on:click={answeredCalled}>oui</button>
    <button class="btn btn-danger" on:click={answeredUncalled}>non</button>
  </div>
{/if} -->
<!-- {#if called == false} -->
  <!-- <Uncalled {called} /> -->
  <section>
    <h2>Qu'est-ce que le terminal</h2>
    <p>
      Il s'agit d'une interface généralement monochrome sous forme de texte,
      permettant d'enter des instructions en ligne de commande. On l'appelle
      simplement interface de lignes de commandes ou
      <i>CLI</i>
      <br />
    </p>
    <h2>Pour commencer</h2>
    <h3>Comment ouvrir le programme</h3>

    <p>Pour ouvrir un terminal, trois possibilités s'offrent à vous</p>
    <ul>
      <li class="text-justify">
        La première (la plus simple) est de sélectionner le programme intitulé
        <i>terminal</i>
        dans le menu.
        <br />NB: l'icone figure peut-être déjà dans le tableau de bord, pensez
        donc à regarder d'abord dans cette barre.
      </li>
      <li>
        Vous pouvez aussi saisir le raccourci clavier
        <i>[CTRL] + [MAJ] + [T]</i>
      </li>
      <li>
        En dernier recours, saisissez la combinaison de touches
        <i>[ALT] + [F2]</i>
        suivie du mot-clé
        <q>terminal</q>
        dans la barre qui vient d'apparaitre, puis appuyez sur
        <i>[ENTREE]</i>
      </li>
    </ul>
    <p>Votre terminal est maintenant prêt à l'emploi</p>
    <h3>Présentation de l'interface</h3>
    <p>
      Vous remarquerez la sobriété de celle-ci: du texte clair sur un fond
      sombre, ou l'inverse. Vous pouvez personnaliser cette vue d'un clic droit
      dans la fenetre et selectionner la ligne
      <i>personnaliser</i>
      En haut ou en bas de l'interface, vous disposez d'une croix
      <i>(+)</i>; celle-ci vous permettra d'ouvrir un onglet supplémentaire.
      Pour fermer ce dernier, vous n'aurez qu'à cliquer sur le signe
      <q>x</q>.
      <br />
    </p>
    <h3>La ligne utilisateur</h3>
    <p>
      Dès l'ouverture du terminal une ligne est apparue, c'est l'invite de
      commande (prompt), comme suit:
    </p>

    <code><Prompt /></code>
    <p>ceci est mon propre prompt</p>

    <ol>
      <li>
        D'abord vous avez un mot suivi de
        <i>@</i>
        puis d'un autre. Le premier mot, vous l'aurez deviné, est l'identifiant
        sous lequel vous êtes connecté. L'autre indique la machine actuelle.
      </li>
      <li>
        Le second terme designe le chemin (<i>~</i>
        est le raccourci pour
        <i>/home/</i>
        suivi de votre identifiant) puis le type d'utilisateur(standard ou
        administrateur):
        <ul>
          <li><i>$</i> pour l'utilistateur standard (par défaut)</li>
          <li>
            <i>#</i>
            pour l'adminisrateur dit aussi root ou sudo. on y reviendra plus
            tard
          </li>
          L'affichage du chemin complet sera votre première commande, que nous
          aborderons très bientôt.
        </ul>
      </li>
    </ol>
    <p>Tout va bien? OK, maintenant vous êtes prêt.e à travailler.</p>

    <a
    href="terminal/learn"
      class="btn btn-info btn-block"
      on:click={() => {
        called = true;
      }}>apprendre le terminal</a>
    <!-- <button
      class="btn btn-info btn-block"
      on:click={() => {
        called = true;
      }}>apprendre le terminal</button> -->
  </section>
<!-- {:else if called === true}
  
{/if} -->

<!-- {called} -->
