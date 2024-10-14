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
    <div class="container ms-min-height">
        <h1 class="mb-3">Page non found</h1>
        <p>Sorry, but the page you are looking for does not exist.</p>
        <p>It might have been moved, renamed, or might never have existed.</p>
        <div class="d-flex gap-2">
            <router-link :to="{name: 'home'}" class="btn btn-dark">Back to Homepage</router-link>
            <router-link :to="{name: 'projects'}" class="btn btn-dark">Back to Projects List</router-link>
        </div>
    </div>
</template>

<style scoped lang="scss">
// @use '../style/partials/variables' as *;
</style>