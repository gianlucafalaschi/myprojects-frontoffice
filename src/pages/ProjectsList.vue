<script>
import axios from 'axios';
import { store } from '../store';
import ProjectCard from '../components/ProjectCard.vue';
import Loader from '../components/Loader.vue';


export default {
  name: 'ProjectsList',
  data() {
    return {
      store,
      projects: [],
      currentPage: 1,
      nextPageUrl: null,
      prevPageUrl: null,
      isLoading: false   // gestisce il caricamento del componente Loader
    }
  },
  components: {
    ProjectCard,
    Loader
  },
  methods: {
    getProjectsFromApi(dataPage) {
      this.isLoading = true;
      // Funzione che prende i projects dall'API 
      axios.get(`${this.store.backendUrl}/api/projects`, {
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

          this.isLoading = false;
        });
    }
  },
  mounted() {
    this.getProjectsFromApi(this.currentPage);
  }
}
</script>

<template>
  <div class="container ms-min-height">
    <h1>All projects</h1>
    
    <div v-if="!isLoading">
      <div class="row row-cols-3">
        <div class="col-12 col-sm-6 col-lg-4" v-for="project in projects" :key="project.id">
          <ProjectCard :projectInfo="project"></ProjectCard>
        </div>
      </div>
      <!-- Pagination -->
      <nav aria-label="Page navigation example">
        <ul class="pagination mt-3">
          <!--se c'è prevPageUrl, stampo il pulsante per la pagina precedente -->
          <li v-if="prevPageUrl" class="page-item">
            <a class="page-link link-dark" @click="getProjectsFromApi(currentPage - 1)">Previous</a>
          </li>
          <!--se c'è nextPageUrl, stampo il pulsante per la pagina successiva -->
          <li v-if="nextPageUrl" class="page-item">
            <a class="page-link link-dark" @click="getProjectsFromApi(currentPage + 1)">Next</a>
          </li>
        </ul>
      </nav>  
      <!-- / Pagination -->
    </div>
    <div v-else>
      <Loader></Loader>
    </div>
  </div>
</template>

<style scoped lang="scss">
//@use '../style/partials/variables' as *;
</style>