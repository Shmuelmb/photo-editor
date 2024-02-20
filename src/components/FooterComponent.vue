<template>
  <footer class="footer">
    <div class="contact-me-icons">
      <a href="https://wa.me/972587300626">
        <i class="fa-brands fa-whatsapp"></i>
      </a>
      <a href="https://github.com/Shmuelmb" target="_blank"
        ><i class="fa-brands fa-github"></i>
      </a>
      <a
        href="https://www.linkedin.com/in/shmuel-cohen-b59501228"
        target="_blank"
        ><i class="fa-brands fa-linkedin"></i>
      </a>
    </div>
  </footer>
</template>

<script setup></script>

<style scoped>
.footer {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  position: fixed;
  bottom: 5px;
  left: 0;
  width: 100%;
  color: white;
}
.contact-me-icons {
  width: 20%;
  height: 10vh;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}
.contact-me-icons i {
  color: white;
}
</style>
