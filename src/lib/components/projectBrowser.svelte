<script>
	export let projects;
	export let project;

	//browsing between projects
	$: previousProject = projects[projects.indexOf(project) - 1];
	$: nextProject = projects[projects.indexOf(project) + 1];
</script>

<div class="project-browser">
	<!-- only show if there is a previous project in the projects array -->
	{#if projects.indexOf(project) > 0}
		<p class="previous"><a href={'/projects/' + previousProject.id}>← Previous</a></p>
	{/if}

	<!-- only show if the current project is not the last project in the projects array -->
	{#if projects.indexOf(project) < projects.length - 1}
		<p class="next"><a href={'/projects/' + nextProject.id}>Next →</a></p>
	{/if}
</div>

<style>
	.project-browser {
		display: flex;
		flex-direction: row;
		margin: 0 auto var(--size-l) auto;
		padding-bottom: var(--size-m);
		width: 90%;
		max-width: 59rem;

		border-bottom: 1px solid var(--c-second-text);
	}

	.project-browser .previous {
		margin-right: auto;
	}

	.project-browser .next {
		margin-left: auto;
	}
</style>
