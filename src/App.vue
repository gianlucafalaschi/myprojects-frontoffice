<script>
  import ProjectsList from './pages/ProjectsList.vue';
  import AppHeader from './components/AppHeader.vue';
  
  export default {
    components: {
      ProjectsList,
      AppHeader,
    },

}
</script>

<template>
  <AppHeader></AppHeader>
  <router-view></router-view>
</template>

<style lang="scss">
@use './style/generic';
//@use './style/partials/variables' as *;  // le variables vanno importate in tutti ii componenti figli se vengono usate

// h1 {
//   color: $main-color;
// }

</style>