<script>
export default {
    name: 'AppHome',
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
      <router-link class="btn btn-light shadow" :to="{name: 'projects'}">Go to our Projects </router-link>
    </div>
  </section>

  <section>
    <div class="container py-1">
      <h1 class="mb-3">Welcome to YourProjects</h1>
      <p>At <strong>YourProjects</strong>, we specialize in creating innovative, user-friendly websites that help businesses thrive in the digital age. Our team of expert designers and developers work closely with you to understand your vision and bring it to life with cutting-edge technology and creative design.</p>
  
      <p>We offer a comprehensive range of services, including:</p> 
  
      <p><strong>Custom Website Design</strong>: Tailored to reflect your brand's unique identity and goals.</p>
      <p><strong>Responsive Development</strong>: Ensuring your site looks and functions perfectly on all devices.</p>
      <p><strong>E-commerce Solutions</strong>: Building robust online stores that drive sales and enhance customer experience.</p>
      <p><strong>SEO Optimization</strong>: Enhancing your website's visibility and ranking on search engines.</p>
      <p><strong>Maintenance & Support</strong>: Providing ongoing support to keep your website running smoothly and securely.</p>
      <p>Our mission is to empower businesses by delivering exceptional web solutions that not only meet but exceed expectations.</p>
      <p class="fs-5"><strong>Join us in designing the future, one website at a time.</strong></p>
    </div>

    <div class="ms-home-photo-box">
    </div>
  </section>
  
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

</style>