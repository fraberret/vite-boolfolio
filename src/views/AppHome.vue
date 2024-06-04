<script>

import axios from 'axios';

export default {
    name: 'AppHome',

    data() {
        return {
            currentIndex: 0,
            projects: [],
            base_api: 'http://127.0.0.1:8000',
            base_projects_url: '/api/projects',
            loading: true
        }
    },
    methods: {

        prev() {
            this.currentIndex--
            if (this.currentIndex < 0) {
                this.currentIndex = this.projects.length - 1

            }
        },
        next() {
            this.currentIndex++
            if (this.currentIndex === this.projects.length) {
                this.currentIndex = 0

            }
        },
        changeThumb(index) {
            this.currentIndex = index
        },

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

    <div class="jumbotron">

        <div class="container">
            <div class="row">
                <div class="socials">

                    <i class="fa-brands fa-github"></i>
                    <i class="fa-brands fa-instagram"></i>
                    <i class="fa-brands fa-linkedin"></i>

                </div>
                <div class="col_4">
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

    <div class="projects">

        <div class="container">
            <h1>Alcuni dei miei progetti</h1>

            <div class="slider">
                <div class="item" v-for="(project, index) in projects" v-show="index === currentIndex">

                    <img :src="base_api + '/storage/' + project.cover_image" alt="" class="card-image">
                    <div class="text">
                        <h3> {{ project.title }}</h3>
                        <p>
                            {{ project.description }}
                        </p>
                    </div>

                </div>
                <div class="thumbs">
                    <div class="prev" @click="prev()"><i class="fa fa-arrow-left" aria-hidden="true"></i></div>
                    <div class="next" @click="next()"><i class="fa fa-arrow-right" aria-hidden="true"></i></div>


                </div>
            </div>

        </div>

    </div>



</template>

<style></style>
