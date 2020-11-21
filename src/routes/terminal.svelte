<script>
  import Prompt from "../components/Prompt.svelte";
  import Code from "../components/Code.svelte";
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
</style>

<svelte:head>
  <title>Terminal</title>
</svelte:head>
<h1>Terminal</h1>
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
    <br />NB: l'icone figure peut-être déjà dans le tableau de bord, pensez donc
    à regarder d'abord dans cette barre.
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
  Vous remarquerez la sobriété de celle-ci: du texte clair sur un fond sombre,
  ou l'inverse. Vous pouvez personnaliser cette vue d'un clic droit dans la
  fenetre et selectionner la ligne
  <i>personnaliser</i>
  En haut ou en bas de l'interface, vous disposez d'une croix
  <i>(+)</i>; celle-ci vous permettra d'ouvrir un onglet supplémentaire. Pour
  fermer ce dernier, vous n'aurez qu'à cliquer sur le signe
  <q>x</q>.
  <br />
</p>
<h3>La ligne utilisateur</h3>
<p>
  Dès l'ouverture du terminal une ligne est apparue, c'est l'invite de commande
  (prompt), comme suit:
</p>

<code><Prompt /></code>
<p>ceci est mon propre prompt</p>

<ol>
  <li>
    D'abord vous avez un mot suivi de
    <i>@</i>
    puis d'un autre. Le premier mot, vous l'aurez deviné, est l'identifiant sous
    lequel vous êtes connecté. L'autre indique la machine actuelle.
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
        pour l'adminisrateur dit aussi root ou sudo. on y reviendra plus tard
      </li>
      L'affichage du chemin complet sera votre première commande, que nous
      aborderons très bientôt.
    </ul>
  </li>
</ol>
<p>Tout va bien? OK, maintenant vous êtes prêt.e à travailler.</p>

<h2>Commandes de base</h2>
<h3>première commande</h3>
<h3>pwd <small>(present working directory - répertoire courant)</small></h3>
<p>
  cette commande désigne le chemin complet dans lequel vous vous trouvez. Entrez
  donc cette instruction et admirez le résultat
</p>
<Code instruction="pwd">
  /home/fabezio
  
</Code>
<p>
  Sympa, non? Et comme vous avez pu le remarquer, le prompt réapparait
  automatiquement. Bien, il est temps d'explorer plus avant les commandes de
  navigation.
</p>
<h3>ls <small>(list)</small></h3>
<p>
  a présent vous allez afficher les fichiers présents dans le répertoire courant
  via
  <i>ls</i>:
</p>
<Code instruction="ls">
  <span class=" inline-block text-primary ">
    <!-- <ul class="inline-block ">  -->
    <span class="item">Bureau</span>
    <span class="item">Document</span>
    <span class="item">Musique</span>
    <span class="item">Vidéo</span>
    <span class="item">Téléchargemnts</span>
    <!-- </ul> -->
  </span>
</Code>
<h3>cd <small>(change directory - changement de répertoire)</small></h3>
<p>
  Le déplacement dans une arborescence est des plus simples, il suffit d'entrer
  la commande
  <i>cd</i>
  suivie du répertoire dans lequel vous voullez vous rendre<br />
  <Code instruction="cd Bureau" >
    <!-- <br><span class="text-success ">fabezio@code4U</span> Bureau/ $  -->
    
  </Code>
  <b>NB</b>: quelle que soit la commmande, vous devrez
  <u><b>toujours</b></u>
  la faire suivre d'un espace, sans quoi le terminal vous renverra un message
  d'erreur:
  <Code instruction="cdBureau">
    <!-- <Prompt />$ cdBureau -->
    
    bash: commande cdBureau non reconnue
    <!-- <Prompt />$ -->
  </Code>
</p>
<h3>afficher les fichiers cachés: ls -a</h3>
<p>Entrez donc la commande donnée ci-dessus et voyez ce que ça donne</p>
<Code path="Bureau" path2="Bureau" instruction="ls -a"> 
  <!-- <Prompt />$ ls -a -->
  <!-- <br /> -->
  <span class=" inline-block text-primary ">
    <!-- <ul class="inline-block ">  -->
    <span class="item">.</span>
    <span class="item">..</span>
    <!-- <span class="item">Musique</span>
                                        <span class="item">Vidéo</span>
                                        <span class="item">Téléchargemnts</span> -->
    <!-- </ul> -->
  </span>
  <!-- <br /> -->
  <!-- <Prompt path="Bureau" />$ -->
</Code>
<p>
  et entez maintenant
  <i>ls ..</i>
  <br />Vous voilà revenu.e dans votre répertoire.
  <br /><q>euhh... pourquoi ça?
  </q>
  <br />eh bien: avant d'avoir la réponse , je vous invite à rentrer la même
  commande.
  <b>STOP!</b>
  appuyez donc sur la flèche du haut: la dernière commande entrée apparait.
  <code>
    <Prompt instruction="ls -a"/>
  </code>
</p>appuyez maintenant sur
<i>[ENTREE]</i>
<Code instruction="ls -a">
  <span class=" inline-block text-primary ">
    <!-- <ul class="inline-block ">  -->
    <span class="item">.</span>
    <span class="item">..</span>
    <span class="item">Bureau</span>
    <span class="item">Document</span>
    <span class="item">Musique</span>
    <span class="item">Vidéo</span>
    <span class="item">Téléchargemnts</span>
    <!-- </ul> -->
  </span>
  
</Code>
<p>
  Eh oui, les deux particularités ont réapparu! Alors de quoi s'agit-il et à
  quoi servent ces extensions. Celle que vous avez utilisée précedemment est un
  <q>raccourci</q>
  pour aller au répertoire dit parent, à savoir celui qui précede le courant.
  <br>
  Quant au point unique, il désigne le répertoire courant.
  vous pouvez le constater en tapant <q>cd .</q>
  <code>
    
    <Prompt instruction="cd ." />
    <br>
    <Prompt />
  </code>
   Voyons maintenant ce que sont ces deux fichiers pointés.
</p>
<h3>Les chemins</h3> 
Le système de fichier est conçu comme une arborescence dans laquelle tout est fichier, dès lors qu'il apparait dans le terminal: fichier simple, dossier, partition, volume ou lecteur. Les dossiers suivent une hiérarchie arborescente, et peuvent contenir tout ce qui vient d'être cité, regroupé en différentes catégories suivant les usages. Notez que je parle d'arborescence, aussi le début de ladite arborescence est appelé racine et répond au symbole <q>/</q>. En descendant dans la hiérarchie, on sépare les noms des dossiers avec ce même symbole, appelé <q>barre oblique</q> ou, plus prosaïquement, <q>slash</q> (sous windows, ce même séparateur est une barre oblique inversée - <q>antislash</q> et il n'y a pas de racine, on utilise la lettre du lecteur, par défaut c pour le lecteur système suivie de deux points puis <q>\</q>, soit "c:\").

<h2>Commandes Administrateur (su / sudo)</h2>
<h3>Gestion des paquets</h3>
