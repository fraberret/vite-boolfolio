<script>
import axios from 'axios';
export default {
    name: 'AppProjects',
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

                <div class="card">


                    <img :src="base_api + '/storage/' + project.cover_image" alt="">

                    {{ project.title }}

                </div>
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped></style>