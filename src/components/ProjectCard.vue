<script>
export default {
  name: 'ProjectCard',
  props:
    [
      'project',
      'base_api'
    ],
  computed: {
    isTruncated() {
      return this.project.description.length > 100;
    },
    truncatedDescription() {
      return this.isTruncated ? this.project.description.slice(0, 100) + '...' : this.project.description;
    }
  }

}
</script>

<template>

  <div class="col">
    <div class="card">
      <img :src="base_api + '/storage/' + project.cover_image" alt="" class="card-image">
      <div class="card-content">
        <h2 class="card-title">{{ project.title }}</h2>
        <p class="card-description">
          {{ truncatedDescription }}
          <router-link v-if="isTruncated" :to="{ name: 'appProjectShow', params: { id: project.id } }"
            class="view-more">View More</router-link>
        </p>
        <router-link :to="{ name: 'appProjectShow', params: { id: project.id } }" class="card-button">View
          Project</router-link>
      </div>
    </div>
  </div>
</template>




<style scoped>
.card {
  height: 100%;
  position: relative;
  border: none;
  border-radius: 10px;
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  background-color: #fff;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
}

.card-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.card:hover .card-image {
  transform: scale(1.05);
}

.card-content {
  padding: 1rem;
}

.card-title {
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
}

.card-description {
  font-size: 1rem;
  color: #666;
  margin-bottom: 1rem;
}

.card-button {
  display: inline-block;
  padding: 0.5rem 1rem;
  font-size: 1rem;
  color: #fff;
  background-color: #DF2935;
  border: none;
  border-radius: 5px;
  text-decoration: none;
  transition: background-color 0.3s ease;
}

.card-button:hover {
  background-color: #DF2935;
}

.view-more {
  color: #DF2935;
  text-decoration: none;
  margin-left: 5px;
}

.view-more:hover {
  text-decoration: underline;
}
</style>
