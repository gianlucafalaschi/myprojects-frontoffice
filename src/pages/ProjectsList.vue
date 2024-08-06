<script>
import ProjectCard from '../components/ProjectCard.vue';
import axios from 'axios';

export default {
  name: 'ProjectsList',
  data() {
    return {
      projects: [],
      currentPage: 1,
      nextPageUrl: null,
      prevPageUrl: null
    }
  },
  components: {
    ProjectCard
  },
  methods: {
    getProjectsFromApi(dataPage) {
      // Funzione che prende i projects dall'API 
      axios.get('http://127.0.0.1:8000/api/projects', {
        params: {
          page: dataPage
        }
      })
        .then((response) => {
          //console.log(response);
          this.projects = response.data.results.data;
          //aggiorno variabile currentPage perndendo i risultati della chiamata Api
          this.currentPage = response.data.results.current_page;

          this.nextPageUrl = response.data.results.next_page_url;
          
          this.prevPageUrl = response.data.results.prev_page_url;


        });

    }
  },
  mounted() {
    this.getProjectsFromApi(this.currentPage);
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
        <!--se c'è prevPageUrl, stampo il pulsante per la pagina precedente -->
        <li v-if="prevPageUrl" class="page-item">
          <a class="page-link" @click="getProjectsFromApi(currentPage - 1)">Previous</a>
        </li>
        <!--se c'è nextPageUrl, stampo il pulsante per la pagina successiva -->
        <li v-if="nextPageUrl" class="page-item">
          <a class="page-link" @click="getProjectsFromApi(currentPage + 1)">Next</a>
        </li>
      </ul>
    </nav>  
    <!-- / Pagination -->
  </div>
</template>

<style scoped lang="scss">
//@use '../style/partials/variables' as *;
</style>