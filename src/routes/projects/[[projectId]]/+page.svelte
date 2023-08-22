<script>
    import { page } from '$app/stores'
    import projects from '$lib/projects.json'

    //id from url
    let { projectId } = $page.params
    //look for the object with projectId id
    let project = projects.find(({ id }) => id === projectId);

    //if there is no project with projectId, use the first project
    if(project == undefined) {
        project = projects[0]
    }
</script>

<h1>this is the case study for { project.title }</h1>