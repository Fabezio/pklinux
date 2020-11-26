<script>
    export let title = "PKLinux"
    export let page = "page?"
</script>

<svelte:head>
<title class="text-capitalize">{title} / {page}</title>
</svelte:head>
<h1>{title}: {page}</h1>