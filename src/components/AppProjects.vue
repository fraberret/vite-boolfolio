<script>

export default {
    name: 'AppProjects',


}

</script>

<template>

    <div class="projects">
        <div class="container_m">
            <div class="projects_title">
                <h1>PROJECTS</h1>
                <div class="underline"></div>
                <p>Here you will find some of the personal projects that I create</p>
            </div>

            <div class="row">
                <div class="col_12 col_m_6">
                    <img src="/images/boolzapp.png" alt="">
                </div>

                <div class="col_12 col_m_6">
                    <div class="project_info">
                        <h3>Boolzapp</h3>

                        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Expedita saepe pariatur quis,
                            recusandae odio quas assumenda, placeat beatae totam architecto dolorem ex aperiam vitae a
                            suscipit dolore nisi? Autem, sapiente.</p>

                        <div class="button">
                            <a href="#aboutme">GitHub</a>
                        </div>

                    </div>



                </div>

            </div>



        </div>
    </div>
</template>


<style>
.projects_title {
    margin: 4rem 0rem;
    text-align: center;
}

.project_info {
    text-align: center;

    & h3 {
        margin-bottom: 1rem;
    }

    & p{
        margin-bottom: 2rem;
    }



}
</style>