<script>
import { RouterLink } from 'vue-router';
import { router } from '../router';

export default {
    name: 'AppHeader',
    data() {
        return {
            menuLinks: [
                {
                    text: 'Home',
                    rootName: 'home'    // name in rooter.js
                },
                {
                    text: 'Projects',
                    rootName: 'projects'
                },
                {
                    text: 'About',
                    rootName: 'about'
                },
            ]
        };
    }
}
</script>

<template>
    <header class="sticky-top">
        <nav class="navbar navbar-expand-md shadow">
            <div class="container-fluid">
                <router-link class="navbar-brand fs-3" :to="{ name: 'home' }"><strong>YourProjects</strong></router-link>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
                    aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarNav">
                    <ul class="navbar-nav">
                        <li v-for="link in menuLinks" class="nav-item">
                            <router-link class="nav-link fw-bold" aria-current="page" :to="{ name: link.rootName }">{{ link.text
                                }}</router-link>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
    </header>
</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;

nav {
    background-color: $gray-color;
}

</style>
