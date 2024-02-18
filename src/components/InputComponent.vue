<template>
  <div>
    <h1>{{ props.card.title }}</h1>
    <input @change="inputHandler" type="file" />
    <div v-if="imageState">
      <ResultComponent :imageState="imageState" :card="card" />
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  card: Object,
});
import ResultComponent from "./ResultComponent.vue";
import { ref } from "vue";

const imageState = ref("src\\assets\\jobiden.webp");
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

<style scoped></style>
