<script>
    import Project from '../components/Project.svelte'

    import projects from '$lib/projects.json'

    let currentAmountOfProjects = 3;
</script>

<section>
    <h1>Projects...</h1>

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
    Show more...
  </button>
  {/if}
</section>