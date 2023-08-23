<script>
    export let project

    let img = project.img_path;

    if(!img) img = "placeholder.svg"

</script>

<section class="project">
    <a href={'/projects/' + project.id}>
        <h3>{ project.title }</h3>
        <p> { project.summary }</p>

        <img src="/images/projects/{ img }" alt="{ project.title } cover picture">
        <p>VIEW CASE STUDY -></p>
    </a>
</section>