<script>
  import Prompt from "./Prompt.svelte";
  export let path = "~";
  export let path2 = "~";
  export let u = "$";
  export let u2 = "$";
  export let instruction = "";
</script>
<style>
    code {
    display: block;
    color: whitesmoke;
    background-color: darkslategray;
    padding: 8px;
    margin: 8px;
  }
</style>

<code>
    <Prompt {path} {u} {instruction} />
    
  <br>
  <Prompt path={path2} u={u2} />
</code>
