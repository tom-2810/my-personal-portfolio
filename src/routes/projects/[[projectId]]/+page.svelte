<script>
	import { page } from '$app/stores';
	import { fly } from 'svelte/transition'
	import projects from '$lib/projects.json';

	import ProjectBrowser from '$lib/components/projectBrowser.svelte';

	//id from url
	$: projectId = $page.params.projectId;
	//look for the object with projectId id
	$: project = projects.find(({ id }) => id === projectId);

	//if there is no project with projectId, use the first project
	$: if (project == undefined) {
		project = projects[0];
	}

	$: img = project.img_path;

	$: if (!img) img = 'placeholder.svg';
</script>

<section in:fly={{ y: 200, duration: 500, delay: 500 }} class="project-page">
	<ProjectBrowser {projects} {project} />
	<div class="hero">
		<h1>{project.title}</h1>
		<img src="/images/projects/{img}" alt="{project.title} cover picture" />
	</div>

	<article>
		<section>
			<h2>Lorem</h2>
			<p>Dolor sit amet.</p>
		</section>
		<section>
			<h2>Lorem</h2>
			<p>Dolor sit amet.</p>
		</section>
		<section>
			<h2>Lorem</h2>
			<p>Dolor sit amet.</p>
		</section>

		<ProjectBrowser {projects} {project} />
	</article>
</section>

<style>
	.project-page {
		display: flex;
		flex-direction: column;
		padding-top: 8rem;
	}

	.hero {
		display: flex;
		gap: var(--size-l);
		flex-direction: column;
		align-items: center;
		margin: 0 auto;
		width: 100%;
		max-width: 59rem;
		height: 100dvh;
		text-align: center;
	}

	.hero h1 {
		height: 2rem;
	}

	.hero img {
		width: 90%;
		max-height: 85%;
		border-radius: var(--radius-l);
		object-fit: cover;
	}
</style>
