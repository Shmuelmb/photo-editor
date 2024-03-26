<template>
  <footer class="footer">
    <div class="flex flex-col"></div>
    <div class="contact-me-icons">
      <a
        href="https://www.linkedin.com/in/shmuel-cohen-b59501228"
        target="_blank"
        >Shmuel cohen <i class="fa-brands fa-linkedin mx-2"></i>
      </a>
      <a href="https://www.linkedin.com/in/roee/" target="_blank"
        >Roee Ben-Moshe<i class="fa-brands fa-linkedin mx-2"></i>
      </a>
      <a href="https://github.com/Shmuelmb" target="_blank"
        ><i class="fa-brands fa-github"></i>
      </a>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  margin-top: 10px;
  color: white;
}
.contact-me-icons {
  width: 20%;
  height: 10vh;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
}
.contact-me-icons a {
  color: white;
  transition: ease-in-out 0.3s;
}

.contact-me-icons a:hover {
  color: rgba(255, 255, 255, 0.381);
}
</style>
