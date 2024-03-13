<script>
	import '../app.pcss';
	import Navbar from '$lib/components/navbar/navbar.svelte';
</script>

<div class="bg-white">
	<header class="absolute inset-x-0 top-0 z-50">
		<Navbar />
	</header>
	<main>
		<slot />
	</main>
	<footer></footer>
</div>
