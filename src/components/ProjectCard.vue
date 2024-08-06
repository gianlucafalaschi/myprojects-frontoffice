<script>
export default {
  name: 'ProjectsCard',
  props: {
    projectInfo: Object
  }
}
</script>

<template>
    <div class="card my-3">
          <!-- <img src="..." class="card-img-top" alt="..."> -->
          <div class="card-body">
            <h5 class="card-title">{{ projectInfo.name }}</h5>
            <div v-if="projectInfo.type">
              <strong>Type</strong>:
              {{ projectInfo.type.name}}
            </div>
            <div v-if="projectInfo.technologies.length > 0">
              <strong>Technologies</strong>:
              <div class="d-flex flex-wrap gap-1">
                <div v-for="technology in projectInfo.technologies" class="badge rounded-pill text-bg-success">{{ technology.name }}</div>
              </div>
            </div>
            
            <p v-if="projectInfo.summary" class="card-text">{{ projectInfo.summary }}</p>
            <router-link :to="{name:'single-project', params: {'slug': projectInfo.slug}}" class="btn btn-primary">Details</router-link>
          </div>
    </div>
</template>

<style scoped lang="scss">
//@use '../style/partials/variables' as *;
</style>