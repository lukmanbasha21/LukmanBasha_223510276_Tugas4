<script setup>
import { defineProps } from "vue";

const props = defineProps({
  laptopData: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <div>
    <h2>Purchase Summary</h2>
    <p>Laptop Name: {{ laptopData.name }}</p>
    <p>Price per Unit: ${{ laptopData.price }}</p>
    <p>Quantity: {{ laptopData.quantity }}</p>
    <p>Total Price: ${{ laptopData.total }}</p>
  </div>
</template>

<style scoped>
h2 {
  color: #42b983;
}
</style>
