<template>
  <input @change="inputImageHandler" type="file" accept="image/*" required />
  <h2>OR</h2>
  <div>
    <form
      class="form"
      @submit.prevent="inputUrlHandler($event.target[0].value)">
      <input placeholder="Enter image url" type="text" required />
      <button type="submit">Submit</button>
    </form>
  </div>

  <div class="cards">
    <div v-for="card in cards" :key="card.id">
      <InputComponent :card="card" :imageState="imageState" />
    </div>
  </div>
</template>

<script setup>
import InputComponent from "./InputComponent.vue";
import { ref } from "vue";
const cards = [
  { imgSrc: "bringThemHomeNow.png", title: "Bring Them Home", id: "a" },
  { imgSrc: "fuckhamas.png", title: "Fuck HAMAS!", id: "b" },
  { imgSrc: "stand.png", title: "Stand With Israel", id: "c" },
];
const imageState = ref("jobiden.jpg");

const inputImageHandler = (e) => {
  const uploadedFile = e.target.files[0];
  const validImageTypes = ["image/gif", "image/jpeg", "image/png"]; // feel free to add more image file types

  if (uploadedFile && validImageTypes.includes(uploadedFile["type"])) {
    const reader = new FileReader();
    reader.onload = (e) => {
      imageState.value = e.target.result;
    };
    reader.readAsDataURL(e.target.files[0]);
  }
};
const inputUrlHandler = (url) => {
  imageState.value = url;
};
</script>

<style scoped>
.form {
  display: flex;

  justify-content: center;
}

.cards {
  display: flex;
  gap: 30px;
  justify-content: center;
  flex-wrap: wrap;
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
</style>
