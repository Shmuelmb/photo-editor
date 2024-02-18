<template>
  <div class="result" :id="props.card.id">
    <img class="baseImg" :src="props.imageState" alt="input-image" />
    <img
      @click="downloadImage"
      class="layout"
      :src="`src\\assets\\${props.card.imgSrc}`"
      alt="layout" />
  </div>
</template>

<script setup>
import html2canvas from "html2canvas";

const props = defineProps({
  imageState: String,
  card: Object,
});
const downloadImage = () => {
  const div = document.getElementById(props.card.id);
  html2canvas(div).then((canvas) => {
    const a = document.createElement("a");
    const imageDataURL = canvas.toDataURL("image/svg");
    a.href = imageDataURL;
    a.download = "profilePhoto.png";
    a.click();
    a.remove();
  });
};
</script>

<style scoped>
.result {
  width: 300px;
  height: 300px;
  border-radius: 50%;
  position: relative;
  width: max-content;
  transition: all 0.2s ease-in-out;
}

.result:hover {
  opacity: 0.5;
}
.baseImg {
  width: 300px;
  height: 300px;
  border-radius: 50%;
  object-fit: contain;
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
