<script>

import AppAbout from '../components/AppAbout.vue';
import AppSkills from '../components/AppSkills.vue';
import AppProjects from '../components/AppProjects.vue';
import AppContacts from '../components/AppContacts.vue';
import AppJumbotron from '../components/AppJumbotron.vue';


export default {
    name: 'AppHome',

    components: {
        AppAbout,
        AppSkills,
        AppProjects,
        AppContacts,
        AppJumbotron

    },
}
</script>

<template>
    <main>

        <AppJumbotron/>
        <AppAbout/>
        <AppProjects/>
        <AppContacts/>

    </main>




</template>


<style>



</style>
