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

    //browsing between projects
    $: previousProject = projects[projects.indexOf(project) - 1]
    $: nextProject = projects[projects.indexOf(project) + 1]
</script>

<h1>this is the case study for { project.title }</h1>

<!-- only show if there is a previous project in the projects array -->
{#if projects.indexOf(project) > 0}
<a href={'/projects/' + previousProject.id}>Previous project</a>
{/if}

<!-- only show if the current project is not the last project in the projects array -->
{#if projects.indexOf(project) < projects.length - 1}
<a href={'/projects/' + nextProject.id}>| Next project</a>
{/if}