<script setup>
import { ref, computed } from "vue";
import { defineEmits } from "vue";

const emit = defineEmits(["update-laptop-data"]);

const name = ref("");
const price = ref(0);
const quantity = ref(0);

const total = computed(() => price.value * quantity.value);

const updateData = () => {
  emit("update-laptop-data", {
    name: name.value,
    price: price.value,
    quantity: quantity.value,
    total: total.value,
  });
};
</script>

<template>
  <div>
    <h2>Enter Laptop Details</h2>
    <form @submit.prevent="updateData">
      <div>
        <label for="name">Laptop Name:</label>
        <input id="name" v-model="name" type="text" required />
      </div>
      <div>
        <label for="price">Price:</label>
        <input id="price" v-model="price" type="number" min="0" required />
      </div>
      <div>
        <label for="quantity">Quantity:</label>
        <input
          id="quantity"
          v-model="quantity"
          type="number"
          min="0"
          required
        />
      </div>
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<style scoped>
h2 {
  color: #35495e;
}
form {
  display: flex;
  flex-direction: column;
}
form > div {
  margin-bottom: 1em;
}
label {
  margin-right: 1em;
}
button {
  background-color: #42b983;
  color: white;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
}
button:hover {
  background-color: #35495e;
}
</style>
