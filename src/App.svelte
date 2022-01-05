<script>
	import Navbar from "./components/Navbar.svelte"
	import Container from "./components/Container.svelte"
</script>

<div class="main-container">
	<Navbar />
	<Container/>
</div>

<style>
	.main-container
	{
		display: flex;
		flex-direction: row;
		flex-wrap: nowrap;
	}
</style>