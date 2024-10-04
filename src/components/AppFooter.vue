<script>
export default {
    name: "AppFooter",
}
</script>

<template>
    <footer class="text-white pt-5 pb-5">
        <div class="container-fluid d-flex">
            <div class="row w-100">
                <div class="col-12 mb-3 col-md-4 text-md-start">
                    <h6>YouProjects</h6>
                    <small><p class="mb-0">YourProjects © Copyright - 2024 - All Rights Reserved</p></small>
                </div>
                <div class="col-12 mb-3  col-md-4 text-md-center">
                    <h6>Social Media</h6>
                    <div class="ms-social-box d-flex justify-content-md-center gap-3">
                        <a href="https://www.facebook.com/"><i class="fa-brands fa-facebook text-white"></i></a>
                        <a href="https://www.instagram.com/"><i class="fa-brands fa-instagram text-white"></i></a>
                        <a href="https://x.com/?lang=en"><i class="fa-brands fa-x-twitter text-white"></i></a>
                        <a href="https://www.youtube.com/"><i class="fa-brands fa-youtube text-white"></i></a>
                    </div>
                </div>
                <div class="col-12 col-md-4 text-md-end">
                    <h6>Privacy Policy</h6>
                    <router-link class="text-decoration-none text-white" :to="{ name: 'privacy'}"><small>Read our Privacy Policy</small></router-link>
                </div>
            </div>
        </div>
    </footer>
</template>

<style>
footer {
    background-color: black;
    box-shadow:0px -1px 23px black; ;
}


</style>