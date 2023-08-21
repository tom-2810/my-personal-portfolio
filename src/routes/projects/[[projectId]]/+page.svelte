<script>
    import { page } from '$app/stores'

    const allProjects = ['123','007','abc']
    const defaultProjectId = 123

    let { projectId = defaultProjectId } = $page.params

    if(!allProjects.includes(projectId)) projectId = defaultProjectId

</script>

<h1>this is project: { projectId }</h1>