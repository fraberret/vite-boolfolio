<script>
import axios from 'axios';
import ProjectCard from '../components/ProjectCard.vue';

export default {

    name: 'AppProjects',

    components: {
        ProjectCard
    },
    data() {
        return {
            projects: [],
            base_api: 'http://127.0.0.1:8000',
            base_projects_url: '/api/projects'
        }
    },
    methods: {
        callApi(url) {
            axios
                .get(url)
                .then(response => {
                    console.log(response.data.projects);
                    this.projects = response.data.projects;
                })
                .catch(err => {
                    console.error(err);
                })
        }
    },
    mounted() {
        let url = this.base_api + this.base_projects_url
        this.callApi(url)
    }
}

</script>

<template>
    <div class="container">
        <div class="row">
            <div class="col" v-for="project in projects.data">

                <ProjectCard></ProjectCard>

            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped></style>