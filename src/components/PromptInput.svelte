<script>
  export let path = "~";
  export let u = "$";
  export let instruction = "";
</script>

<style>
  input {
    background: darkslategray;
    border: none;
  }
  
</style>

<div>

    <span class="text-success ">fabezio@code4U</span>:<span
    class="text-primary">{path}</span>{u}
    <input class="text-light" type="text" bind:this={instruction}>
</div>
