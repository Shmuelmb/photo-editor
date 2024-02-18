<template>
  <div class="cards">
    <div v-for="card in cards" :key="card.id">
      <InputComponent :card="card" />
    </div>
  </div>
</template>

<script setup>
import InputComponent from "./InputComponent.vue";
const cards = [
  { imgSrc: ".../assets/a.png", title: "Bring Them Home Now !", id: "a" },
  { imgSrc: ".../assets/a.png", title: "Fuck HAMAS!", id: "b" },
  { imgSrc: ".../assets/a.png", title: "Stand With Israel", id: "c" },
];
</script>

<style scoped>
.cards {
  display: flex;
  gap: 10px;
  justify-content: center;
}
</style>
