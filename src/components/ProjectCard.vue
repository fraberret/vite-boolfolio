<script>
export default {
  name: 'ProjectCard',
  props:
    [
      'project',
      'base_api'
    ],

}
</script>

<template>

  <div class="col">
    <router-link :to="{ name: 'appProjectShow', params: { id: project.id } }">
      <div class="card">
        <img :src="base_api + '/storage/' + project.cover_image" alt="">
        {{ project.title }}
      </div>
    </router-link>

  </div>
</template>


<style></style>
