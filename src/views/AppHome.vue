<script>

import AppAbout from '../components/AppAbout.vue';
import AppProjects from '../components/AppProjects.vue';
import AppContacts from '../components/AppContacts.vue';
import AppJumbotron from '../components/AppJumbotron.vue';


export default {
    name: 'AppHome',

    components: {
        AppAbout,
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
