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
  { imgSrc: "bringThemHomeNow.png", title: "Bring Them Home Now", id: "a" },
  { imgSrc: "fuckhamas.png", title: "Fuck HAMAS!", id: "b" },
  { imgSrc: "stand.png", title: "Stand With Israel", id: "c" },
];
</script>

<style scoped>
.cards {
  display: flex;
  gap: 30px;
  justify-content: center;
  flex-wrap: wrap;
}
</style>
