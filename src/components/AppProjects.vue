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

    <!-- Projects Section -->
    <div class="projects">
        <div class="container_m">

            <!-- Projects title -->
            <div class="projects_title">
                <h1 class="section_heading">PROJECTS</h1>
                <div class="underline"></div>
                <p>Here you will find some of the personal projects that I create</p>
            </div>

            <!-- Projects -->
            <div v-for="project in projects" class="container_project">
                <div class="row">

                    <!-- Projects Image -->
                    <div class="col_12 col_m_6">
                        <img :src='project.image' :alt="project.name + ' screenshot'">
                    </div>

                    <!-- Projects Info -->
                    <div class="col_12 col_m_6">
                        <div class="project_info">
                            <h3>{{ project.name }}</h3>
                            <p>{{ project.description }}</p>

                            <!-- Projects Link Button -->
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
    width: 80%;
    margin: auto;
    text-align: center;

    & h3 {
        margin-bottom: 1rem;
    }

    & p {
        margin-bottom: 2rem;
    }



}
</style>