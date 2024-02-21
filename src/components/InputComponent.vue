<template>
  <div class="input-component">
    <h1>{{ props.card.title }}</h1>
    <input @change="inputHandler" type="file" required />
    <div v-if="imageState">
      <ResultComponent :imageState="imageState" :card="card" />
      <p :class="imageState !== 'jobiden.jpg' ? 'download-title' : 'none'">
        To download your new Linkedin profile photo click on the image
      </p>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  card: Object,
});
import ResultComponent from "./ResultComponent.vue";
import { ref } from "vue";

const imageState = ref("jobiden.jpg");
const inputHandler = (e) => {
  console.log(props.card.imgSrc);
  if (e.target.files && e.target.files[0]) {
    const reader = new FileReader();
    reader.onload = (e) => {
      imageState.value = e.target.result;
    };
    reader.readAsDataURL(e.target.files[0]);
  }
};
</script>

<style scoped>
.input-component {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 20px;
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
  transition: ease-in-out 0.2s;
}
.input-component:hover {
  scale: 1.01;
}
input {
  position: relative;
  height: 40px;
  width: 200px;
  cursor: pointer;
}
input:hover {
  opacity: 0.8;
}
input:before {
  background: #000000;
  border: 1px solid #fff;
  content: "Upload Profile Photo...";
  color: #fff;
  font-weight: bold;
  line-height: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  pointer-events: none;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

input:invalid:before {
  content: "Choose your image";
}
input:valid:before {
  content: "Image Uploaded";
  background: #000000;
}
.download-title {
  font-weight: bold;
  font-size: 10px;
  text-align: center;
  display: block;
}
.none {
  display: none;
}
</style>
