<script>
export default {
  name: 'AppHome',
  data() {
    return {

    }
  }
}
</script>
<!-- HERO -->
<template>
  <section class="ms-hero d-flex justify-content-center align-items-center shadow">
    <div class="ms-inside-hero text-white text-center">
      <h1 class="mb-5">Designing the Future, One Website at a Time</h1>
      <router-link class="btn btn-light ms-button-hover shadow" :to="{ name: 'projects' }">Go to our
        Projects</router-link>
    </div>
  </section>
  <!--/ HERO -->
  
  <!-- SERVICES -->
  <section>
    <div class="container py-1">
      <h1 class="my-3 text-center fst-italic">Welcome to YourProjects</h1>
      <p>At <strong>YourProjects</strong>, we specialize in creating innovative, user-friendly websites that help
        businesses thrive in the digital age. Our team of expert designers and developers work closely with you to
        understand your vision and bring it to life with cutting-edge technology and creative design.</p>

      <div class="ms-bg-gray rounded shadow p-3">
        <p>We offer a comprehensive range of services, including:</p>

        <p><strong>Custom Website Design</strong>: Tailored to reflect your brand's unique identity and goals.</p>
        <p><strong>Responsive Development</strong>: Ensuring your site looks and functions perfectly on all devices.</p>
        <p><strong>E-commerce Solutions</strong>: Building robust online stores that drive sales and enhance customer
          experience.</p>
        <p><strong>SEO Optimization</strong>: Enhancing your website's visibility and ranking on search engines.</p>
        <p class="mb-0"><strong>Maintenance & Support</strong>: Providing ongoing support to keep your website running
          smoothly and
          securely.</p>
      </div>
    </div>
  </section>
  <!--/ SERVICES -->    
    <!-- CAROUSEL -->
    <section>
      <div id="carouselExampleAutoplaying" class="carousel slide pt-3" data-bs-ride="carousel">
        <div class="carousel-inner">
          <div class="carousel-item active ms-image-carousel" data-bs-interval="2000">
            <img src="../assets/brooke-cagle--uHVRvDr7pg-unsplash.jpg" class="d-block w-100" alt="a group of people chatting">
          </div>
          <div class="carousel-item ms-image-carousel" data-bs-interval="2000">
            <img src="../assets/ian-schneider-TamMbr4okv4-unsplash (1).jpg" class="d-block w-100" alt="a written on the sidewalk: passion led us here">
          </div>
          <div class="carousel-item ms-image-carousel" data-bs-interval="2000">
            <img src="../assets/jason-goodman-Oalh2MojUuk-unsplash (1).jpg" class="d-block w-100" alt="a company meeting">
          </div>
          <div class="carousel-item ms-image-carousel" data-bs-interval="2000">
            <img src="../assets/carlos-muza-hpjSkU2UYSU-unsplash (1).jpg" class="d-block w-100" alt="a laptop, tables and graphs on the screen ">
          </div>
        </div>
        <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleAutoplaying"
          data-bs-slide="prev">
          <span class="carousel-control-prev-icon bg-dark" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleAutoplaying"
          data-bs-slide="next">
          <span class="carousel-control-next-icon bg-dark" aria-hidden="true"></span>
          <span class="visually-hidden">Next</span>
        </button>
      </div>
    </section>
    <!-- /CAROUSEL -->
    <!-- BOTTOM -->
    <section>
      <div class="container pt-5">
        <p>Our mission is to empower businesses by delivering exceptional web solutions that not only meet but exceed
          expectations.</p>
        <p class="fs-5 fst-italic"><strong>Join us in designing the future, one website at a time.</strong></p>
        <div class="d-flex justify-content-center">
          <router-link class="btn btn-dark shadow mb-5" :to="{ name: 'projects' }">Our Projects</router-link>
        </div>
      </div>
    </section>
    <!--/ BOTTOM -->
</template>

<style scoped lang="scss">
@use '../style/partials/variables' as *;

.ms-hero {
  width: 100%;
  height: 400px;
  background-image: url(../assets/zachary-nelson-98Elr-LIvD8-unsplash.jpg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

.ms-inside-hero {
  background-color: rgba(0, 0, 0, 0.157);
  border-radius: 10px;
  padding: 20px;
}

.ms-home-photo-box {
  width: 100%;
  height: 400px;
  background-image: url(../assets/brooke-cagle--uHVRvDr7pg-unsplash.jpg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

.ms-image-carousel {
  height: 40vw;

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
  }
}

.ms-bg-gray {
  background-color: $gray-color;
}

</style>