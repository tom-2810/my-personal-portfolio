<script>
    import Project from '../components/Project.svelte'

    import projects from '$lib/projects.json'

    let currentAmountOfProjects = 3;
</script>

<section>
    <h2 id="projects"><a href="#projects">Projects</a></h2>

    <div class="projects">
        <!-- append all projects -->
        {#each projects.slice(0, currentAmountOfProjects) as project}
            <!-- pass down the current project -->
            <Project { project } />
        {/each}
    </div>

    {#if currentAmountOfProjects < projects.length}
    <button class="second-btn"
    on:click={() => currentAmountOfProjects = currentAmountOfProjects + 3}>
    Show more
  </button>
  {/if}
</section>

<style>
    .projects {
        display: flex;
        flex-direction: column;
        gap: var(--size-xl);
    }
</style>