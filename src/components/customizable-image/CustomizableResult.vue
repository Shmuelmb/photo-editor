<script setup>
import CustomImage from '../customizable-image/CustomImage.vue';
import CustomSentence from '../customizable-image/CustomSentence.vue';
import ReusableBanner from '../customizable-image/ReusableBanner.vue';
</script>

<template>
  <div class="custom">
    <CustomImage />
    <ReusableBanner />
    <CustomSentence />
  </div>
</template>

<style scoped>
.custom {
  position: relative;
  width: 300px;
  height: 300px;
  place-self: end;
}
</style>
