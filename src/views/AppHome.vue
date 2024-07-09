<script>

import axios from 'axios';

export default {
    name: 'AppHome',

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

    <!-- Jumbotron -->
    <div class="jumbotron">
        <div class="container">
            <div class="row">

                <!-- Social section -->
                <div class="socials">
                    <a href="https://github.com/fraberret" target="_blank"><i class="fa-brands fa-github"></i></a>
                    <a href="https://www.instagram.com/_.cccesco/" target="_blank"><i class="fa-brands fa-instagram"></i></a>
                    <a href="https://www.linkedin.com/in/francesco-berretta-dev/" target="_blank"><i class="fa-brands fa-linkedin"></i></a>
                </div>

                <!-- Bio section -->
                <div class="col_6">
                    <h1>
                        Ciao, <br> sono Francesco Berretta

                    </h1>

                    <p class="profession">
                        <strong>Jr Full-Stack Web-Developer</strong>
                    </p>

                    <p class="bio">Da sempre sono una persona molto curiosa e appassionata di <strong>Problem
                            Solving</strong> e di
                        tecnologia. Con un background nel mondo dell'audio come fonico, ho affinato le mie capacità nel
                        risolvere problemi complessi e nell'adattarmi a nuove sfide con creatività e determinazione.
                        Nel 2024 ho deciso di dare una <strong>svolta</strong> alla mia vita e ho intrapreso questo
                        fantastico percorso da <strong>Web Developer</strong> che mi ha permesso di apprendere molte
                        skill e
                        di <strong>sviluppare</strong> un'altra grande passione.</p>

                </div>

            </div>
        </div>
    </div>

    <!-- Projects Sections -->
    <div class="projects_home">
        <div class="container">
            <h1>Alcuni dei miei progetti</h1>

        </div>
    </div>



</template>

<style></style>
