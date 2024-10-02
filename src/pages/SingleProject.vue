<script>
import axios from 'axios';
import { store } from '../store';
import Loader from '../components/Loader.vue';

export default {
    name: 'SingleProject',
    components: {
        Loader
    },
    data() {
        return {
            store,
            project: null,
            isLoading: false  // gestisce il caricamento del componente Loader
        }; 
    },
    methods: {
    getProjectDetails() {
        this.isLoading = true;
     // Funzione che prende il project dall'API  
     //<!-- $route.params.slug    sintassi per leggere lo slug della pagina -->       
     axios.get(`${this.store.backendUrl}/api/projects/${this.$route.params.slug}`)  
        .then((response) => {
          console.log(response);
          // se response.data.success è true mostriamo il single project
          if(response.data.success) {
            this.project = response.data.project;
          } else{
          // altrimenti redirect alla pagina 404
          this.$router.push({name: 'not-found'})  
          }

          this.isLoading = false;
        });
    }
  },
  mounted() {
    this.getProjectDetails();
  }
}
</script>

<template>
    <div class="container ms-min-height">
        <div v-if="project && !isLoading">
            <h1>{{project.name}}</h1>
            <div v-if="project.client_name"><strong>Client name</strong>: {{ project.client_name }}</div>
            <div v-if="project.type">
                <strong>Type</strong>: {{ project.type.name }}
            </div>
            <div v-if="project.technologies.length > 0">
                <div class="mb-2"><strong>Technologies</strong>:</div>
                <div class="d-flex gap-1">
                    <div v-for="technology in project.technologies" class="badge rounded-pill text-bg-success"> {{ technology.name }}</div>
                </div>
            </div>

            <div class="mt-4" v-if="project.cover_image">
                <img :src="`${store.backendUrl}/storage/${project.cover_image}`" :alt="project.name">
            </div>
            
            <P class="mt-4">{{ project.summary }}</P>
        </div>
        <div v-else>
            <Loader></Loader>
        </div>
        <div>
            <router-link :to="{name:'projects'}" class="btn btn-primary my-4">Back</router-link>
        </div>
    </div>

</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;
</style>