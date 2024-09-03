<script>

import axios from 'axios';
import AppAbout from '../components/AppAbout.vue';
import AppSkills from '../components/AppSkills.vue';


export default {
    name: 'AppHome',

    components: {
        AppAbout,
        AppSkills
    },


    data() {
        return {

            projects: [],
            base_api: 'http://127.0.0.1:8000',
            base_projects_url: '/api/projects',
            loading: true
        }
    },
    methods: {



        callApi(url) {
            axios
                .get(url)
                .then(response => {
                    this.projects = response.data.projects.data;
                    console.log(this.projects);
                    this.loading = false
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
    <main >
        <!-- Jumbotron -->
        <div id="#home" class="jumbotron">
            <div class="jumbotron_content d-flex align-center">

                
                 <h1>Hi, I'm Francesco Berretta</h1>
                

                <div class="jumbotron_info">

                    <p>A Result-Oriented Web Developer building and managing Websites and Web Applications that leads to
                        the success of the overall product</p>

                </div>

                <div class="jumbotron_button">
                    <a href="#aboutme">Projects</a>
                </div>

            </div>
        </div>

        <AppAbout id="aboutme"></AppAbout>
        

    </main>




</template>

<style>



</style>
