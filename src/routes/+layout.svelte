<script>
	import Nav from '../components/nav.svelte';
</script>

<Nav />

<div class="page">
	<slot />
</div>

<style>
	:root {
		--main-color: rgb(29, 206, 255);
		--accent-color: rgb(31, 93, 134);
		--text-color: rgb(220, 220, 220);
	}
	:global(body) {
		background-color: rgb(40, 40, 40);
		color: var(--text-color);
		padding: 0;
		margin: 0;
		height: 200vh;
	}
	:global(h1) {
		color: var(--main-color);
		font-family: 'Rochester', cursive;
	}

	.page {
		margin-top: 4rem;
	}
</style>
