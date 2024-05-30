<script>

import axios from 'axios';

export default {
  name: 'App',
  data() {
    return {
      projects: [],
      base_api: 'http://127.0.0.1:8000/api/projects'
    }
  },
  methods: {
    callApi(url) {
      axios
        .get(url)
        .then(response => {
          console.log(response);
          this.projects = response.data;
        })
        .catch(err => {
          console.error(err);
        })
    }
  },
  mounted() {
    let url = this.base_api
    this.callApi(url)
  }
}
</script>

<template>
  <div>

  </div>
</template>

<style></style>
