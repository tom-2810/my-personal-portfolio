<script>
    import { page } from '$app/stores'

    let { projectId = 'default' } = $page.params

    if(projectId == 'doesnotexist')
    projectId = 'default'

</script>

<h1>this is project { projectId }</h1>