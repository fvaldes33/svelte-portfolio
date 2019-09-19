<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>

<style>
	main {
		box-sizing: border-box;
		height: 100%;
		position: relative;
		width: 100%;
	}

	@media screen and (max-width: 400px) {
		:global(body) {
			font-size: 10px;
		}
	}
</style>

<!-- <Nav {segment}/> -->

<main>
	<slot></slot>
</main>
