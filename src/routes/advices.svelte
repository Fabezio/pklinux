<h1>Conseils et précautions</h1>
  <p>Avant toute chose, prenez bien soin de verifier l'espace restant sur le volume destiné à recevoir votre toute nouvelle distribution. Il faut a minima 15 Go, 60 Go si vous avez prévu de mettre beaucoup (mais alors vraiment beaucoup) de programmes; 40 Go c'est raisonnable. Suite de quoi vous pouvez démarrer votre installation, laquelle se découpe en plusieurs étapes: </p>
  <ol>
    <li>le choix des langue et disposition clavier. Pour la langue c'est toujours pareil; là ou ça change, c'est la disposition clavier: Windows et Mac ne prévoient pas de dispo (un layout) autre que azety ou qwerty (ou variantes spécifiques); cette fois ces subtilités sont prévues dès le départ. Et si avez l'habitude de taper en bépo, dvorak ou autre, cette option est disponible. Plus besoin de rechercher un programme pour configuer le layout.</li>
    <li>la localisation (important pour accorder votre horloge au fuseau)</li>
    <li>le mode d'installation. Cette fois c'est un peu moins évident, il y a plusieurs options:
      <ul>
        <li>suivant les distros, le programe d'installation propose de placer votre OS à coté de celle déja présente, auquel cas il adaptera les volumes. C'est le plus simple. </li>
        <li>Si par contre vous avez prévu de remplacer l'intégralité du volume, il faudra au préalable s'assurer que vos propres fichiers sont sauvegardés sur un autre. </li>
        <li>la troisième option consiste à personnaliser le disque. Un bon tuto au préalable devrait vous aider si vous n'êtes pas rompu.e au partitionnement. Une chose à savoir est que par défaut la partition par défaut de Linux (volume racine <em>
            <q>/</q></em>) est du format <em>ext4</em>. C'est actuellement le plus indiqué pour ce système d'exploitation. Vous aurez donc intérêt, si vous partitionnez manuellement, à selectionner ce format.</li>
        <li>En ce qui concerne les ficheiers personnels, vous devez <b>toujours </b> disposer d'une partition secondaire. Cette dernière vous servira pour une nouvelle installation ultérieure et demeurera intacte sans avoir à tout déplacer (cette partition aura la référence <em>/home</em>). Si vous voulez y stocker des données d'un autre volume, c'est possible après l'installation. Linux détecte la plupart des flashs et disques durs.
          En outre vous pouvez utiliser une partition déjà présente et lui attribuer le label <em>/home</em>. Pour plus de sécurité il vaut tout de même mieux sauvegarder le contenu sur un volume externe ou un autre interne.
        </li>
      </ul>
    </li>
    <li>Vient ensuite la personnalisation: le choix de votre identifiant, éventuellement le nom complet, le mot de passe (à confirmer). Généralement vous avez les droits d'administration par défaut (via la commande <em>sudo</em>), mais il est parfois nécessaire de le préciser si demandé (option <em>root</em>). Ce faisant vous pourrez absolument tout faire. Important: cette étape ne se fait sur certaines distributions qu'une fois l'installation terminée, l'ordinateur redémarré (ex: <em>Fedora</em>).</li>
    <li>L'installation démarre. Patientez quelques minutes.</li>
    <li>Dernière étape: le gestionnaire de démarrage (parfois cette option apparait avec le choix d'installation). Si vous avez plusieurs volumes ou systèmes d'exploitation, il sera demandé si vous voulez installer <em>Grub </em> (c'est le nom du gestionnaire); confirmez. S'il demande sur quel volume vous voulez le placer, ce sera celui qui héberge Linux.</li>
    <li>Même chose pour le gestionnaire de paquet, répondez par l'affirmative, sinon vous ne pourrez rien installer. Concernant le depot miroir, si la question est posée, laissez tel quel (vous pourrez toujours le configurer plus tard)</li>
  </ol>
  <p>Voilà, vous avez installé Linux. Pas si dur, n'est-ce pas? En plus ça aura pris moins de quinze minutes. A présent redémarrez et profitez!</p>
<!-- </h1> -->
<style>
  li, ul {
    /* list-style: inside; */
    position: relative;
    right: 10px;

  }
</style>