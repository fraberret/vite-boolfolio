<script>
export default {
  name: 'ProjectCard',
  props:
    [
      'project',
    ],

}
</script>

<template>

  <div class="col">
    <div class="card">
      <img :src="base_api + '/storage/' + project.cover_image" alt="">
      {{ project.title }}
    </div>
  </div>
</template>


<style></style>
