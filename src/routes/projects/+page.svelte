<script lang="ts">
	import Project from '../../components/project.svelte';
	import type { PageData } from './$types';

	export let data: PageData;
</script>

<div class="container">
	<h1>Projects</h1>

	<p>Here are some projects I've worked on:</p>
</div>
<div class="projects">
	{#each data.projects as project}
		<Project {project} />
	{/each}
</div>

<style>
	.container {
		margin-left: 1rem;
	}
	.projects {
		margin-top: 5rem;
	}
</style>
