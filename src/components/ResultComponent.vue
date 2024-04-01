<template>
  <div class="result">
    <div>
      <div :id="props.card.id">
        <div class="relative">
          <img class="baseImg" :src="props.imageState" alt="input-image" />
          <img
            @click="downloadImage"
            class="layout"
            :src="`${props.card.imgSrc}`"
            alt="layout" />
          <div v-if="loading" class="absolute top-[40%] right-[40%]">
            <span class="loader"></span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { toPng } from "html-to-image";
import { ref } from "vue";
const props = defineProps({
  imageState: String,
  card: Object,
});
const loading = ref(false);

const downloadImage = () => {
  loading.value = true;
  toPng(document.getElementById(props.card.id), { cacheBust: false })
    .then((dataUrl) => {
      const link = document.createElement("a");
      link.download = "my-linkedin-profile.png";
      link.href = dataUrl;
      link.click();
      link.remove();
      loading.value = false;
    })
    .catch((err) => {
      loading.value = false;

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
.loader {
  width: 48px;
  height: 48px;
  border: 5px solid #fff;
  border-bottom-color: transparent;
  border-radius: 50%;
  display: inline-block;
  box-sizing: border-box;
  animation: rotation 1s linear infinite;
}

@keyframes rotation {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
