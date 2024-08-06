<script>
import axios from 'axios';

export default {
    name: 'SingleProject',
    data() {
        return {
            project: null
        }; 
    },
    methods: {
    getProjectDetails() {
     // Funzione che prende il project dall'API  
     //<!-- $route.params.slug    sintassi per leggere lo slug della pagina -->       
     axios.get(`http://127.0.0.1:8000/api/projects/${this.$route.params.slug}`)  
        .then((response) => {
          //console.log(response);
          this.project = response.data.project;
        });
    }
  },
  mounted() {
    this.getProjectDetails();
  }
}
</script>

<template>
    <div class="container">
        <div v-if="project">
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
                <img :src="`http://127.0.0.1:8000/storage/${project.cover_image}`" :alt="project.name">
            </div>
            
            <P class="mt-4">{{ project.summary }}</P>
        </div>
    </div>

</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;
</style>