<script>
    import { page } from '$app/stores'
    import projects from '$lib/projects.json'

    //id from url
    $: projectId = $page.params.projectId
    //look for the object with projectId id
    $: project = projects.find(({ id }) => id === projectId);

    //if there is no project with projectId, use the first project
    $: if(project == undefined) {
        project = projects[0]
    }

    $: img = project.img_path;

    $: if(!img) img = "placeholder.svg"

    //browsing between projects
    $: previousProject = projects[projects.indexOf(project) - 1]
    $: nextProject = projects[projects.indexOf(project) + 1]
</script>

<section>
    
    <div class="hero">

        <div class="project-intro">
            <!-- only show if there is a previous project in the projects array -->
            <div class="browser">
                {#if projects.indexOf(project) > 0}
    <p><a href={'/projects/' + previousProject.id}>Previous ←</a></p>
    {/if}
            </div>
    
    
    <h1>{ project.title }</h1>

    <!-- only show if the current project is not the last project in the projects array -->
    <div class="browser">
        {#if projects.indexOf(project) < projects.length - 1}
    <p><a href={'/projects/' + nextProject.id}>→ Next</a></p>
    {/if}
    </div>
    
        </div>
    

    <img src="/images/projects/{ img }" alt="{ project.title } cover picture">
    
    </div>
    
    
    
</section>

<style>
    section {
        display: flex;
        flex-direction: column;

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
        padding-top: 8rem;
        text-align: center;
    }

    .project-intro {
        display: flex;
        align-items: center;
        width: 70%;
        justify-content: space-between;
    }

    .project-intro .browser {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 10rem;
        height: 4rem;
    }

    .hero img {
        width: 90%;
        max-height: 85%;
        border-radius: var(--radius-l);
        object-fit: cover;
    }
</style>