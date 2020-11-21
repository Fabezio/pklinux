<script>
    import Prompt from './Prompt.svelte'
    export let path = "~"
    export let path2 = "~"
</script>

<Prompt {path}/>
<slot/>
<Prompt path={path2}/>
