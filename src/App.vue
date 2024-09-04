<script>

import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'
import AppHome from './views/AppHome.vue';

export default {
  name: 'App',

  components: {
    AppHeader,
    AppHome,
    AppFooter
  }

}
</script>

<template>

  <AppHeader></AppHeader>
  
  <AppHome></AppHome>

  <AppFooter></AppFooter>

</template>

<style></style>
