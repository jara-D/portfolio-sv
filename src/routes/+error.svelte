<script lang="ts">
	import { page } from '$app/stores';
</script>

<div>
	<h1>{$page.status}</h1>
	{#if $page.status === 404}
		<p>Page not found</p>
    {:else if $page.status === 500}
        <p>Internal server error</p>
    {:else}
        <p>Unknown error</p>
    {/if}

	<a href="/">Home</a>
</div>

<style>
	div {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin-top: 50px;
	}
	h1,
	p {
		font-size: calc(1rem + 2vw);
	}
	a {
		background-color: var(--main-color);
		padding: 10px;
		border-radius: 0.5rem;
		color: var(--text-color);
		font-size: calc(1rem + 1vw);
		text-decoration: none;
	}
</style>
