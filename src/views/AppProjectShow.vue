<script>
import axios from 'axios';

export default {
    name: 'AppProjectShow',


    data() {
        return {

            base_api: 'http://127.0.0.1:8000',
            base_projects_url: '/api/projects',
            project: [],
            loading: true
        }
    },
    methods: {


    },
    mounted() {

        const url = this.base_api + this.base_projects_url + `/${this.$route.params.id}`
        console.log(url);

        axios
            .get(url)
            .then(response => {
                if (response.data.success) {
                    this.project = response.data.response
                    this.loading = false
                    console.log(this.project);
                } else {

                }
            })

    }

}
</script>

<template>

    <div class="container " v-if="!loading">
        <img :src="base_api + '/storage/' + project.cover_image" alt="">
        {{ project.title }}
    </div>

    <div class="container " v-else>
        Loading....
    </div>


</template>



<style lang="scss" scoped></style>