<script>
	import '../app.pcss';
	import Navbar from '$lib/components/Navbar.svelte';
</script>

<div class="bg-background">
	<Navbar />
	<main>
		<slot />
	</main>
	<footer></footer>
</div>
