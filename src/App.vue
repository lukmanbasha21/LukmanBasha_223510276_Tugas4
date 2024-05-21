<script setup>
import { ref } from "vue";
import LaptopForm from "./components/LaptopForm.vue";
import PurchaseSummary from "./components/PurchaseSummary.vue";

const laptopData = ref({
  name: "",
  price: 0,
  quantity: 0,
  total: 0,
});

const updateLaptopData = (data) => {
  laptopData.value = data;
};
</script>

<template>
  <div>
    <h1>Laptop Purchase</h1>
    <LaptopForm @update-laptop-data="updateLaptopData" />
    <PurchaseSummary v-if="laptopData.name" :laptopData="laptopData" />
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
h1 {
  color: #42b983;
}
</style>
