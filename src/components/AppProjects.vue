<script>
import { projects } from '../../project';

export default {
    name: 'AppProjects',

    data() {
        return {
            projects
        }
    }


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

            <div v-for="project in projects" class="container_project">
                <div  class="row">
                    <div class="col_12 col_m_6">
                        <img :src='project.image' alt="">
                    </div>

                    <div class="col_12 col_m_6">
                        <div class="project_info">
                            <h3>{{ project.name }}</h3>

                            <p>{{ project.description }}</p>

                            <div class="button">
                                <a :href='project.link' target="_blank" rel="noopener noreferrer">GitHub</a>
                            </div>

                        </div>

                    </div>

                </div>

            </div>



        </div>
    </div>
</template>


<style>
.projects_title {
    margin-bottom: 4rem;
    text-align: center;
}

.project_info {
    text-align: center;

    & h3 {
        margin-bottom: 1rem;
    }

    & p {
        margin-bottom: 2rem;
    }



}
</style>