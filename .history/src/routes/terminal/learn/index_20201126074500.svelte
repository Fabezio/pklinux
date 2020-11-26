<script>
  // import Prompt from "../../components/Prompt.svelte";
  // import PromptInput from "../../components/PromptInput.svelte";
  import Code from "../../../components/Code.svelte";
  import Alert from "../../../components/UI/Alert.svelte";

  import { files } from "../files.js";
  // files = files.sort()
  // import Uncalled from "../../components/terminal/Uncalled.svelte";
  let called = undefined;
  let answered = false;
  function answeredUncalled() {
    called = false;
    answered = true;
  }
  function answeredCalled() {
    called = true;
    answered = true;
  }
  let instruction;
  // import Clock from "../components/UI/Clock.svelte";
</script>

<style>
  /* code {
    display: block;
    color: whitesmoke;
    background-color: darkslategray;
    padding: 8px;
    margin: 8px;
  } */

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
  <title>Terminal | Mode d’emploi</title>
</svelte:head>
<h1>Terminal : Mode d’emploi</h1>
<section id="learn">
  <h2>Commandes de base</h2>
  <h3>première commande</h3>
  <h3>pwd <small>(present working directory - répertoire courant)</small></h3>
  <p>
    Cette commande désigne le chemin complet dans lequel vous vous trouvez.
    Entrez donc cette instruction et admirez le résultat:
  </p>
  <Code {instruction}>/home/fabezio</Code>
  <p>
    Sympa, non? Et comme vous avez pu le remarquer, le prompt réapparait
    automatiquement. Bien, il est temps d'explorer plus avant les commandes de
    navigation.
  </p>
  <h3>ls <small>(list)</small></h3>
  <p>
    À présent vous allez afficher les fichiers présents dans le répertoire
    courant via
    <i>ls</i>:
  </p>
  <Code instruction="ls">
    <span class=" inline-block  ">
      {#each files as file}
        {#if file.name.charAt(0) != '.'}
          <span
            class="item mr-2 {file.type == 'folder' ? 'text-primary' : 'text-light'}">{file.name}</span>
        {/if}
      {/each}
      <!-- <span class="item">Bureau</span>
        <span class="item">Documents</span>
        <span class="item">Musique</span>
        <span class="item">Vidéos</span>
        <span class="item">Téléchargements</span> -->
    </span>
  </Code>
  <h3>cd <small>(change directory - changement de répertoire)</small></h3>
  <p>
    Le déplacement dans une arborescence est des plus simples, il suffit
    d'entrer la commande
    <i>cd</i>
    suivie du répertoire dans lequel vous voullez vous rendre<br />
    <Code instruction="cd Bureau" path2="~/Bureau" />
    <!-- </Code> -->

    <b>NB</b>: quelle que soit la commmande, vous devrez
    <u><b>toujours</b></u>
    la faire suivre d'un espace, sans quoi le terminal vous renverra un message
    d'erreur:
    <Code instruction="cdBureau">bash: commande cdBureau non reconnue</Code>
  </p>
  <h3>afficher les fichiers cachés: ls -a</h3>
  <p>Entrez donc la commande donnée ci-dessus et voyez ce que ça donne</p>
  <Code path="~/Bureau" path2="~/Bureau" instruction="ls -a">
    <span class=" inline-block text-primary ">
      <span class="item">.</span>
      <span class="item">..</span>
    </span>
  </Code>
  <p>
    et entez maintenant
    <i>cd ..</i>
    <Code instruction="cd .." path="~/Bureau" />
    Vous voilà revenu.e dans votre répertoire. Vous doutez? pas de problème, entrez
    <i>pwd</i>:

    <Code instruction="pwd" />
    <Alert>
      Mais que s'est-il passé, au juste? 

    </Alert>
    <p>eh bien: avant d'avoir la réponse, je vous invite à rentrer la même
    commande.
    <div class="alert alert-danger rounded-pill mx-2"><i class="far fa-warning-circle mr-2"></i>
      <b>STOP!</b>
    </div>
    <p>Appuyez donc sur la flèche du haut: la dernière commande entrée apparait;
    validez:

    <Code instruction="ls -a">
      <span class=" inline-block  ">
        {#each files as file}
          <!-- {#if file.name.charAt(0) != "."} -->
          <span
            class="item mr-2 {file.type == 'folder' ? 'text-primary' : 'text-light'}">{file.name}</span>
          <!-- {/if} -->
        {/each}
      </span>
    </Code>
  </p>
  <p>
    Eh oui, les deux particularités ont réapparu! Alors de quoi s'agit-il et à
    quoi servent ces extensions? Celle que vous avez utilisée précédemment est
    un
    <q>raccourci</q>
    menant au répertoire dit parent, à savoir celui qui précede le courant.
    <br />
    Quant au point unique, il désigne le répertoire courant. vous pouvez le
    constater en tapant
    <q >cd .</q>
    <Code instruction="cd ." />

    Voyons maintenant ce que sont ces deux fichiers pointés.
  </p>
  <h3>Les chemins</h3>
  <p>
    Le système de fichier est conçu comme une arborescence dans laquelle tout
    est fichier, dès lors qu'il apparait dans le terminal: fichier simple,
    dossier, partition, volume ou lecteur. Les dossiers suivent une hiérarchie
    arborescente, et peuvent contenir tout ce qui vient d'être cité, regroupé en
    différentes catégories suivant les usages. Notez que je parle
    d'arborescence, aussi le début de ladite arborescence est appelé racine et
    répond au symbole
    <q>/</q>. En descendant dans la hiérarchie, on sépare les noms des dossiers
    avec ce même symbole, appelé
    <q>barre oblique</q>
    ou, plus prosaïquement,
    <q>slash</q>
    (sous windows, ce même séparateur est une barre oblique inversée -
    <q>antislash</q>
    et il n'y a pas de racine, on utilise la lettre du lecteur, par défaut c
    pour le lecteur système suivie de deux points puis
    <q>\</q>, soit "c:\"). Cette suite de dossiers est appelée chemin: en effet,
    il définit l'emplacement exact du dossier à atteindre.
    <br />Maintenant, il y a un point important à connaître en matière de
    navigation via le terminal: la saisie du chemin peut se faire de deux
    manières:
  </p>
  <dl>
    <dt>en absolu</dt>
    <dd>
      on tape l'intégralité de puis la racine, ex:
      <Code instruction="cd /home/fabezio/Documents" path2="~/Documents" />
    </dd>
    <dt>en relatif</dt>
    <dd>
      on part du dossier courant pout-r en atteindre un autre par exemple du
      dossier Documents vers le Bureau:
      <Code instruction="cd ../Bureau" path="~/Documents" path2="~/Bureau" />
    </dd>
  </dl>
  <div class="alert alert-warning rounded-pill mx-2"><i class="far fa-question-circle mr-2"></i>OK mais il se passe quoi en cas d'erreur?</div>
    <p>
    Essayons avec un nom de dossier erroné:

    <Code instruction="cd ../documents" path="~/Bureau" path2="~/Bureau">
      -bash: cd: documents: Pas de dossier ou fichier correspondant
    </Code>
    comme vous pouvez le voir, une erreur d'entrée est très bien gérée. Autre
    chose: le terminal est sensible à la casse, en clair il distingue les
    minuscles des majuscules; donc en entrant par esemple un cd documents, bash
    (le programme du terminal) vous retournerait une erreur similaire à la
    précédente.
  </p>
  <Alert>

    OK, mais qu'en est-il des fichiers cachés?
  </Alert>
    <p>
    Refaites donc un
    <i> ls </i>
    <Code instruction="ls -a">
      <span class=" inline-block text-primary ">
        <!-- <span class="item">.</span>
      <span class="item">..</span> -->
        <span class="item">Bureau</span>
        <!-- <span class="item text-light">.bashrc</span> -->
        <span class="item">Documents</span>
        <span class="item">Musique</span>
        <span class="item">Vidéos</span>
        <span class="item">Téléchargements</span>
      </span>
    </Code>
    Maintenant un
    <i>ls -a</i>
    <Code instruction="ls -a">
      <span class=" inline-block text-primary ">
        <span class="item">.</span>
        <span class="item">..</span>
        <span class="item">Bureau</span>
        <span class="item text-light">.bashrc</span>
        <span class="item">Document</span>
        <span class="item">Musique</span>
        <span class="item">Vidéos</span>
        <span class="item">Téléchargements</span>
      </span>
    </Code>
    En plus des fichiers '.' et '..', vous pouvez voir '.bashrc' en clair. Le
    point en début de fichier désigne un fichier caché. En général, il s'agit de
    fichiers de configuration, il en va de même pour des dossiers (vous en
    verrez apparaitre de plus en plus au fur et à mesure des installations).
    Bref, tout ce qui est pointé au début n'apparaitra pas en appelant une liste
    classique.
  </p>
  <h3>les listes détaillées</h3>
  <p>
    Il est également possible d'appeler de telles listes, avec l'option "-l"
  </p>
  <Code instruction="ls -l">
    total
    {files.length-4}
    <table>
      {#each files as file}
        {#if file.name.charAt(0) != '.'}
          <tr>
            <td class="mr-2 ">{file.privileges}</td>
            <!-- <td class="mr-2 ">{file.length}</td> -->
            <td class="mr-2 ">{file.user}</td>
            <td class="mr-2 ">{file.group}</td>
            <td class="mr-2 ">{file.size}</td>
            <td
              class="mr-2 {file.type == 'folder' ? 'text-primary' : 'text-light'}">
              {file.name}
            </td>
          </tr>
          <!-- <span class="item mr-2 {file.type=='folder'? 'text-primary' : 'text-light'}">{file.name}</span> -->
        {/if}
      {/each}
      <!-- <tr>
        <td class="">drwxr-xr-x</td>
        <td class="">3</td>
        <td class="">fabezio</td>
        <td class="">4096</td>
        <td class="">nov.</td>
        <td class="">9</td>
        <td class="">22:19</td>
        <td class=" text-primary">Bureau</td>
      </tr>
      <tr>
        <td class="">drwxr-xr-x</td>
        <td class="">4</td>
        <td class="">fabezio</td>
        <td class="">fabezio</td>
        <td class="">4096</td>
        <td class=" ">nov.</td>
        <td class=" ">15</td>
        <td class=" ">13:38</td>
        <td class=" text-primary">Documents</td>
      </tr>
      <tr>
        <td>drwxr-xr-x</td>
        <td>3</td>
        <td>fabezio</td>
        <td>fabezio</td>
        <td>4096</td>
        <td>nov.</td>
        <td>10</td>
        <td>09:32</td>
        <td class="text-primary">Images</td>
      </tr>
      <tr>
        <td>drwxr-xr-x</td>
        <td>4</td>
        <td>fabezio</td>
        <td>fabezio</td>
        <td>4096</td>
        <td>oct.</td>
        <td>30</td>
        <td>10:41</td>
        <td class="text-primary">Musique</td>
      </tr>
      <tr>
        <td>drwxr-xr-x</td>
        <td>2</td>
        <td>fabezio</td>
        <td>fabezio</td>
        <td>4096</td>
        <td>oct.</td>
        <td>6</td>
        <td>16:47</td>
        <td class="text-primary">Public</td>
      </tr>
      <tr>
        <td>drwxr-xr-x</td>
        <td>3</td>
        <td>fabezio</td>
        <td>fabezio</td>
        <td>4096</td>
        <td>oct.</td>
        <td>22</td>
        <td>10:00</td>
        <td class="text-primary">snap</td>
      </tr>
      <tr>
        <td>drwxr-xr-x</td>
        <td>14</td>
        <td>fabezio</td>
        <td>fabezio</td>
        <td>4096</td>
        <td>nov.</td>
        <td>19</td>
        <td>13:31</td>
        <td class="text-primary">Téléchargements</td>
      </tr>
      <tr>
        <td>drwxr-xr-x</td>
        <td>2</td>
        <td>fabezio</td>
        <td>fabezio</td>
        <td>4096</td>
        <td>nov.</td>
        <td>9</td>
        <td>22:33</td>
        <td class="text-primary">Vidéos</td>
      </tr> -->
    </table>
    <!-- drwxr-xr-x  3 fabezio fabezio  4096 nov.   9 22:19  Bureau
drwxr-xr-x  5 fabezio fabezio  4096 nov.   9 19:49  Codes
drwxr-xr-x  4 fabezio fabezio  4096 nov.  15 13:38  Documents -->

    <!-- <div class="row" /> -->
  </Code>

  <!-- </p> -->
  <p />

  <h2>Commandes Administrateur (su / sudo)</h2>
  <h3>Gestion des paquets</h3>
</section>
