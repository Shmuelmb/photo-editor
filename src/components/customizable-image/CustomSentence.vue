<script setup>
const banner = 'Work with us';
const arrayOfLetterObjects = banner.split('').map((letter, i) => ({self: letter, index: i}));
</script>
<template>
  <div class="custom__sentence">
    <span v-for="letter in arrayOfLetterObjects" class="l" :style="`rotate:${letter.index * 12}deg; bottom:${letter.index * 1}px; right:${letter.index * 1}px`" :key="letter.index">
      {{ letter.self }}
    </span>
  </div>
</template>
<style scoped>
.custom__sentence {
  position: relative;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  rotate: 45deg;
}
[class^='l'] {
  z-index: 50;
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translate(-50%, 5%);
  font-size: 35px;
}
</style>
