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
    <title>Terminal | Lister ses fichers</title>
  </svelte:head>
  <h1>Terminal : Mode d’emploi</h1>