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
  mounted() {
    axios
      .get(this.base_api)
      .then(response => {
        console.log(response);
      })
  }
}
</script>

<template>
  <div>

  </div>
</template>

<style></style>
