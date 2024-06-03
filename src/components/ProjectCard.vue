<script>
export default {
  name: 'ProjectCard'
}
</script>

<template>

  <div class="col">
    <div class="card">

      <div class="card">


<img :src="base_api + '/storage/' + project.cover_image" alt="">

{{ project.title }}

</div>

    </div>
  </div>
</template>


<style></style>
