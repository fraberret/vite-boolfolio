<script>

import AppAbout from '../components/AppAbout.vue';
import AppSkills from '../components/AppSkills.vue';
import AppProjects from '../components/AppProjects.vue';
import AppContacts from '../components/AppContacts.vue';
import test from '../components/test.vue';


export default {
    name: 'AppHome',

    components: {
        AppAbout,
        AppSkills,
        AppProjects,
        AppContacts,
        test

    },
}
</script>

<template>
    <main>

        <test/>

        <!-- Jumbotron Section -->
        <div id="home" class="jumbotron">
            <div class="jumbotron_content">

                <!-- Jumbotron Title -->
                <h1>Hi, I'm Francesco Berretta</h1>

                <!-- Jumbotron Info -->
                <div class="jumbotron_info">
                    <p>A Result-Oriented Web Developer building and managing Websites and Web Applications that leads to
                        the success of the overall product</p>
                </div>

                <!-- Jumbotron Button -->
                <div class="button">
                    <a href="#projects">Projects</a>
                </div>
            </div>
        </div>


        <AppAbout/>
        <AppProjects/>
        <AppContacts/>

    </main>




</template>


