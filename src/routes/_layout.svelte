<script>
	import Nav from '../components/Nav.svelte';
	import Footer from '../components/Footer.svelte';

	export let segment;
</script>

<style>
	/* main {
		position: relative;
		max-width: 56em;
		background-color: white;
		padding: 2em;
		margin: 0 auto;
		box-sizing: border-box;
		text-align: left;
	} */
	/* @media screen and (min-width: 1200px) {
		main {
			width: 1200px;

		}
	} */
</style>

<Nav {segment}/>

<main class="container mt-5">
	<slot></slot>
</main>

<Footer />