<script>
    export let project
</script>

<section class="project">
    <a href={'/projects/' + project.id}>
        <h2>{ project.title }</h2>
        <p> { project.summary }</p>
    </a>
</section>