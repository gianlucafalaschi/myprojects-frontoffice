<script>
export default {
    name: 'NotFound',
    data() {
        return {

        }
    }
}

</script>

<template>
    <div class="container">
        <h1 class="mb-3">Page non found</h1>
        <div class="d-flex flex-column gap-2">
            <router-link :to="{name: 'home'}">Back to Homepage</router-link>
            <router-link :to="{name: 'projects'}">Back to Projects List</router-link>
        </div>
    </div>
</template>

<style scoped lang="scss">
// @use '../style/partials/variables' as *;
</style>