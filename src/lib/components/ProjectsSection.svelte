<script>
	import Project from '../components/Project.svelte';

	import projects from '$lib/projects.json';

	let currentAmountOfProjects = 3;

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
				on:click={() => (currentAmountOfProjects = currentAmountOfProjects + 3)}
			>
				Show more
			</button>
		{/if}
	</div>
</section>

<style>
	.projects {
		display: grid;
		grid-template-columns: repeat(9, 1fr);
		column-gap: var(--size-xl);
		row-gap: var(--size-xxl);

		margin: 0 auto 7rem auto;
		width: 100%;
		max-width: 53rem;
		padding: 0 5vw;
	}

	.more {
		display: flex;
		justify-content: space-around;
	}

	@media (max-width: 580px) {
		.projects {
			display: flex;
			flex-direction: column;
			gap: var(--size-xl);
		}
	}
</style>
