<script>
import ProjectCard from '../components/ProjectCard.vue';
import axios from 'axios';

export default {
  name: 'ProjectsList',
  data() {
    return {
      projects: []
    }
  },
  components: {
    ProjectCard
  },
  methods: {
    getProjectsFromApi() {
      // Funzione che prende i projects dall'API 
      axios.get('http://127.0.0.1:8000/api/projects')
        .then((response) => {
          //console.log(response);
          this.projects = response.data.results;
        });

    }
  },
  mounted() {
    this.getProjectsFromApi()
  }
}
</script>

<template>
  <div class="container">
    <h1>All projects</h1>

    <div class="row row-cols-3">
      <div class="col" v-for="project in projects" :key="project.id">
        <ProjectCard :projectInfo="project"></ProjectCard>
      </div>
    </div>
    <!-- Pagination -->
    <nav aria-label="Page navigation example">
      <ul class="pagination">
        <li class="page-item"><a class="page-link">Previous</a></li>

        <li class="page-item"><a class="page-link">Next</a></li>
      </ul>
    </nav>  
    <!-- / Pagination -->
  </div>
</template>

<style scoped lang="scss">
//@use '../style/partials/variables' as *;
</style>