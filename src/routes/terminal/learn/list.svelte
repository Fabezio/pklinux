<script>
    // import Prompt from "../../components/Prompt.svelte";
    // import PromptInput from "../../components/PromptInput.svelte";
    import Code from "../../../components/Code.svelte";
    import Alert from "../../../components/UI/Alert.svelte";
    import Head from "../../../components/UI/Head.svelte";
  
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
    export let title
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
  
  <Head {title} page="Lister des fichers" />
  