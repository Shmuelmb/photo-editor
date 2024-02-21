<script setup>
import FooterComponent from "./components/FooterComponent.vue";
import HeaderComponent from "./components/HeaderComponent.vue";
import ChooseYourEditComponent from "./components/ChooseYourEditComponent.vue";
</script>

<template>
  <div class="center-col">
    <HeaderComponent />
    <ChooseYourEditComponent />
    <FooterComponent />
  </div>
</template>

<style scoped>
.center-col {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
}
</style>
