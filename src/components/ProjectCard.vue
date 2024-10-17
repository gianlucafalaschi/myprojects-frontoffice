<script>
import { store } from '../store';

export default {
  name: 'ProjectsCard',
  props: {
    projectInfo: Object
  },
  data() {
    return {
      store,
    };
  }
}
</script>

<template>
    <div class="card my-3 shadow">
          <img :src="`${store.backendUrl}/storage/${projectInfo.cover_image}`" class="card-img-top ms-card-img" :alt="projectInfo.name">
          <div class="card-body text-center">
            <h5 class="card-title fs-1 mb-3 text-truncate">{{ projectInfo.name }}</h5>
            <div class="ms-type-container badge bg-secondary fs-6" v-if="projectInfo.type">
              <strong>Type</strong>:
              <span>{{ projectInfo.type.name}}</span>
            </div>
            <div v-if="projectInfo.technologies.length > 0">
              <div class="ms-badge-technology-container d-flex flex-wrap fs-5 gap-1">
                <div v-for="technology in projectInfo.technologies" class="badge rounded-pill text-bg-dark">{{ technology.name }}</div>
              </div>
            </div>
            
            <!-- <p v-if="projectInfo.summary" class="card-text">{{ projectInfo.summary }}</p> -->
            <div class="d-flex justify-content-center mt-4">
              <router-link :to="{name:'single-project', params: {'slug': projectInfo.slug}}" class="btn btn-dark">Details</router-link>
            </div>
          </div>
    </div>
</template>

<style scoped lang="scss">
//@use '../style/partials/variables' as *;

/* CARD IMAGE  */
.ms-card-img {
  height: 200px;
  object-fit: cover;
}

.card {
  transition: transform 0.5s ease; 
  &:hover {
    transform: scale(1.03);
    border: 1px solid black;
  } 
}
/*  */


.card-body {
  position: relative;
}

.ms-badge-technology-container {
  position: absolute;
  top: 0px;
  transform: translate(0, -50%)
}

</style>