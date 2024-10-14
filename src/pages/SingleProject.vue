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
                    if (response.data.success) {
                        this.project = response.data.project;
                    } else {
                        // altrimenti redirect alla pagina 404
                        this.$router.push({ name: 'not-found' })
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
        <div class="row">
            <div v-if="project && !isLoading" class="col-12">
                <h1 class="text-center my-5">{{ project.name }}</h1>
                <div class="row"> 
                    <div class="col-12 col-lg-6"> 
                        <div class="ms-image-box shadow" v-if="project.cover_image">
                            <img class="ms-main-image" :src="`${store.backendUrl}/storage/${project.cover_image}`"
                                :alt="project.name">
                        </div>
                    </div>
                    <div class="col-6 offset-3 offset-lg-0 mt-3 mt-lg-0"> 
                        <div v-if="project.client_name"><strong>Client name</strong>: {{ project.client_name }}</div>
                        <div v-if="project.type">
                            <strong>Type</strong>: {{ project.type.name }}
                        </div>
                        <div v-if="project.technologies.length > 0">
                            <div class="mb-2"><strong>Technologies</strong>:</div>
                            <div class="d-flex gap-1">
                                <div v-for="technology in project.technologies"
                                    class="badge rounded-pill text-bg-dark fs-6"> {{ technology.name }}</div>
                            </div>
                        </div>
                        <div class="ms-summary-box rounded mt-4 shadow">
                            <P class="m-0 p-3">{{ project.summary }}</P>
                        </div>
                    </div>
                </div>
            </div>
            <div v-else>
                <Loader></Loader>
            </div>
            <div class="container">
                <router-link :to="{ name: 'projects' }" class="btn btn-dark my-4">Back</router-link>
            </div>
        </div>
    </div>


</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;


.ms-image-box {
    border-radius: 10px;
    overflow: hidden;
    transition: transform 0.5s ease;
    &:hover {
        transform: translateY(-5px);
        border: 2px solid black;
    }
}


.ms-main-image {
    width: 100%;
    height: auto;
    max-height: 653px;
    object-fit: cover;
    
}

.ms-summary-box {
    background-color: $gray-color;
    transition: transform 0.5s ease;
    &:hover {
        transform: translateY(-5px);
        border: 1px solid black;

    }
}
</style>