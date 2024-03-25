<template>
  <section id="hero" class="d-flex align-items-center">
    <div
      id="heroCarousel"
      class="container carousel carousel-fade"
      data-bs-ride="carousel"
      data-bs-interval="5000">
      <!-- Slide 1 -->
      <div class="carousel-item active">
        <div class="carousel-container">
          <h2
            class="animate__animated animate__fadeInDown"
            style="color: black">
            RELEASE THE <span>HOSTAGES</span>
          </h2>
          <p class="animate__animated animate__fadeInUp" style="color: black">
            Remind the world to demand to release our hostages by placing this
            badge on your social media profile photo!
          </p>
        </div>
      </div>

      <!-- Slide 2 -->
      <div class="carousel-item">
        <div class="carousel-container">
          <h2
            class="animate__animated animate__fadeInDown"
            style="color: black">
            SPREAD AWARENESS
          </h2>
          <p class="animate__animated animate__fadeInUp" style="color: black">
            Remind the world to demand to release our hostages by placing this
            badge on your social media profile photo!
          </p>
        </div>
      </div>

      <a
        class="carousel-control-prev"
        href="#heroCarousel"
        role="button"
        data-bs-slide="prev">
        <span
          class="carousel-control-prev-icon bx bx-chevron-left"
          aria-hidden="true"></span>
      </a>

      <a
        class="carousel-control-next"
        href="#heroCarousel"
        role="button"
        data-bs-slide="next">
        <span
          class="carousel-control-next-icon bx bx-chevron-right"
          aria-hidden="true"></span>
      </a>
    </div>
  </section>
</template>

<style scoped>
section {
  width: 100vw !important;
  margin-bottom: 50px;
}
</style>
