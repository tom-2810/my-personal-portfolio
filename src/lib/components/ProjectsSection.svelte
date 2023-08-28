<script>
	import Project from '../components/Project.svelte';

	import projects from '$lib/projects.json';

	let currentAmountOfProjects = 4;
</script>

<section id="projects">
	<h2><a href="#projects">Projects</a></h2>

	<div class="projects">
		<!-- append all projects -->
		{#each projects.slice(0, currentAmountOfProjects) as project}
			<!-- pass down the current project -->
			<Project {project} />
		{/each}
	</div>

	<div class="more">
		{#if currentAmountOfProjects < projects.length}
			<button
				class="second-btn"
				on:click={() => (currentAmountOfProjects = currentAmountOfProjects + 6)}
			>
				Show more
			</button>
		{/if}
	</div>
</section>

<style>
	.projects {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(20rem, 1fr));
		gap: var(--size-l);

		margin: 0 auto;
		width: 100%;
		max-width: 59rem;
		padding: 0 2vw;
	}

	.more {
        display: flex;
        justify-content: space-around;
	}
</style>
