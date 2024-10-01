<script>
  import ProjectsList from './pages/ProjectsList.vue';
  import AppHeader from './components/AppHeader.vue';
  import AppFooter from './components/AppFooter.vue';
  
  export default {
    components: {
      ProjectsList,
      AppHeader,
      AppFooter

    },

}
</script>

<template>
  <AppHeader></AppHeader>
  <router-view></router-view>
  <AppFooter></AppFooter>
</template>

<style lang="scss">
@use './style/generic';
//@use './style/partials/variables' as *;  // le variables vanno importate in tutti ii componenti figli se vengono usate

// h1 {
//   color: $main-color;
// }

</style>