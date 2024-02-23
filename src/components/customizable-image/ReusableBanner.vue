<script setup></script>

<template>
  <div class="custom__banner"></div>
</template>

<style scoped>
.custom__banner {
  width: 100%;
  height: 100%;
  color: white;
  font-size: 35px;
}
.custom__banner::before {
  content: "";
  position: absolute;
  inset: 0;
  border-radius: 50%;
  padding: 35px; /* control the border thickness */
  background: linear-gradient(20deg, green 0% 15%, transparent 75% 100%);
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor;
  mask-composite: exclude;
  pointer-events: none;
}
</style>
