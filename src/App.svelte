<script>
	import Header from "./Header.svelte";
	import Content from "./Content.svelte";
	import Footer from "./Footer.svelte";
</script>

<!-- HTML start -->
<div class="container">
	<Header />
	<Content />
	<Footer />
</div>
<!-- HTML end -->

<style>
.container {
	width: 100%;
	height: 100%;
	display: flex;
	flex-direction: column;
	align-items: center;
}
</style>