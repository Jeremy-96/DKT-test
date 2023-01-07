<script>
	import Header from "./Header.svelte";
	import SportsList from "./SportsList.svelte";
	import Footer from "./Footer.svelte";

	/**
	 * Get a lsit of all sports
	 */
	const promise = getAllSports();

	async function getAllSports(){
  	const res = await fetch('https://sports.api.decathlon.com/sports/');
  	const json = await res.json();

  	return json.data;
  }
</script>

<!-- HTML start -->
<div class="container">
	<Header />

	{#await promise}
		<p>Chargement...</p>
	{:then sports}
	<SportsList sports={sports} />
	{:catch error}
		<p>Une erreur s'est produite : {error.message}</p>
	{/await}

	<Footer />
</div>
<!-- HTML end -->

<style>
.container {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	min-height: 100%;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: space-between;
}
</style>