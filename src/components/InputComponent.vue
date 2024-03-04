<template>
  <div class="input-component">
    <h1>{{ props.card.title }}</h1>
    <div v-if="imageState">
      <ResultComponent :imageState="imageState" :card="card" />
    </div>
  </div>
</template>

<script setup>
import ResultComponent from "./ResultComponent.vue";
const props = defineProps({
  card: Object,
  imageState: String,
});
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

.download-title {
  font-weight: bold;
  font-size: 15px;
  text-align: center;
  display: block;
}
.none {
  display: none;
}
</style>
