<script>
	import { page } from '$app/stores';
	import { fly, scale } from 'svelte/transition';
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

<section class="project-page">
	<ProjectBrowser {projects} {project} />
	<div class="hero" in:fly={{ y: 100, duration: 700, delay: 300 }}>
		<h1 in:fly={{ y: 200, duration: 900, delay: 1000 }}>{project.title}</h1>
		<img in:scale={{ duration: 400, delay: 250 }} src="/images/projects/{img}" alt="{project.title} cover picture" />
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

<div in:fly={{ y: 200, duration: 900, delay: 1000 }} class="action-btns">
	<a href="#" class="action-btn">Visit live</a>
	<a target="_blank" href="https://github.com/tom-2810/" class="second-btn">Open GitHub repo</a>
</div>

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
		margin: 0 auto var(--size-xxl) auto;
		width: 100%;
		max-width: 59rem;
		text-align: center;
	}

	.hero h1 {
		position: relative;
		height: 2rem;
		z-index: -1;
	}

	.hero img {
		width: 90%;
		max-width: 42rem;
		border-radius: var(--radius-l);
		object-fit: cover;
	}
	.action-btns {
		position: fixed;
		bottom: var(--size-m);
		left: 50%;
		transform: translateX(-50%);
		width: max-content;
		z-index: 1;
	}
</style>
