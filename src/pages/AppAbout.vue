<script>
export default {
    name: 'AppAbout',
    data() {
        return {
        }
    }
}

</script>

<template>
    <section class="ms-hero d-flex justify-content-center align-items-center shadow">
        <div class="ms-inside-hero text-white text-center">
            <h1 class="mb-5">Designing the Future, One Website at a Time</h1>
            <router-link class="btn btn-light ms-button-hover shadow" :to="{ name: 'projects' }">Go to our Projects </router-link>
        </div>
    </section>

    <section>
        <div class="py-1">
            <div class="container">
                <h1 class="mb-3">About YourProjects</h1>
                <p>Welcome to <strong>YourProjects</strong>! We are a passionate team of web development experts
                    dedicated
                    to bringing your digital dreams to life. Our mission is to create stunning, user-friendly websites
                    that
                    not only look great but also perform exceptionally well.</p>
            </div>
        </div>

        <div class="ms-bg-color-dark pt-1">
            <div class="container">
                <h2 class="mb-3">Who We Are</h2>
                <p>At YourProjects, we believe that every business deserves a unique online presence. Our team consists
                    of
                    talented designers, developers, and strategists who work collaboratively to deliver customized web
                    solutions tailored to your specific needs. With years of experience in the industry, we pride
                    ourselves
                    on our ability to transform ideas into reality.</p>
            </div>

            <div class="ms-about-photo-box">
            </div>
        </div>

        <div class="ms-bg-color-light py-1">
            <div class="container">
                <h2 class="mb-3">Our Approach</h2>
                <p>We take a client-centric approach to every project. From the initial consultation to the final
                    launch, we
                    work closely with you to understand your goals and deliver a website that exceeds your expectations.
                    Our
                    process is transparent, and we keep you informed at every stage, ensuring a smooth and stress-free
                    experience.</p>
            </div>
        </div>

        <div class="ms-bg-color-dark py-1">
            <div class="container">
                <h2 class="mb-3">Why Choose Us?</h2>
                <ul class="list-group list-group-flush">
                    <li class="list-group-item ms-bg-color-dark "><strong>Expertise</strong>: Our team has a proven track record of
                        delivering high-quality web solutions.</li>
                    <li class="list-group-item ms-bg-color-dark"><strong>Innovation</strong>: We stay ahead of industry trends to provide
                        cutting-edge solutions.</li>
                    <li class="list-group-item ms-bg-color-dark"><strong>Customer Satisfaction</strong>: Your satisfaction is our top
                        priority, and we go the extra mile to ensure you are happy with the final product.</li>
                    <li class="list-group-item ms-bg-color-dark"><strong>Affordability</strong>: We offer competitive pricing without
                        compromising on quality.</li>
                </ul>
            </div>
        </div>

        <div class="ms-bg-color-light py-1">
            <div class="container">
                <p class="mt-3 fs-5">Join the many satisfied clients who have trusted <strong>YourProjects</strong> to
                    elevate their online presence.</p>
                <p class="fs-5"><strong>Let's create something amazing together!</strong></p>
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;

.ms-hero {
    width: 100%;
    height: 400px;
    background-image: url(../assets/daria-shevtsova-zbWFT4eVopE-unsplash.jpg);
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
}

.ms-inside-hero {
    background-color: rgba(0, 0, 0, 0.157);
    border-radius: 10px;
    padding: 20px;
}


.ms-bg-color-dark {
    background-color: $gray-color;
}

.ms-bg-color-light {
    background-color: none;
}

.ms-about-photo-box {
    width: 100%;
    height: 400px;
    background-image: url(../assets/brooke-cagle-g1Kr4Ozfoac-unsplash.jpg);
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
}
</style>