<template>
  <div class="result">
    <div :id="props.card.id">
      <img class="baseImg" :src="props.imageState" alt="input-image" />
      <img
        @click="downloadImage"
        class="layout"
        :src="`${props.card.imgSrc}`"
        alt="layout" />
    </div>
  </div>
</template>

<script setup>
import { toPng } from "html-to-image";
const props = defineProps({
  imageState: String,
  card: Object,
});
const downloadImage = () => {
  toPng(document.getElementById(props.card.id), { cacheBust: false })
    .then((dataUrl) => {
      const link = document.createElement("a");
      link.download = "my-linkedin-profile.png";
      link.href = dataUrl;
      link.click();
      link.remove();
    })
    .catch((err) => {
      console.log(err);
    });
};
</script>

<style scoped>
.result {
  width: 300px;
  height: 300px;
  border-radius: 50%;
  position: relative;
  transition: all 0.2s ease-in-out;
}

.result:hover {
  opacity: 0.5;
}
.baseImg {
  width: 300px;
  height: 300px;
  border-radius: 50%;
  object-fit: cover;
}
.layout {
  position: absolute;
  top: 0;
  left: 0;
  width: 300px;
  height: 300px;
  border-radius: 50%;
  cursor: pointer;
}
</style>
