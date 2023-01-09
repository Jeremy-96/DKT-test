<script>
	/**
	 * Imports of all components and packages needed to run the application
	 */
	import { Router, Route } from "svelte-routing";
	import Header from "./Header.svelte";
	import SportsList from "./SportsList.svelte";
	import Footer from "./Footer.svelte";
  import Sport from "./Sport.svelte";


	const promise = getAllSports(); 

	/**
	 * Get a list of all sports using fetch api
	 * @async
	 * @function getAllSports
	 * @return {json.data} json file containing data of all sports
	 * @author Jérémy Thonon <jeremythonon96@hotmail.com>
	 */
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
	
	<Router>
		<Route path="/sport/:id" let:params >
			<Sport id="{params.id}" />
		</Route>
	</Router>

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