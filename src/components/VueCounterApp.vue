<script setup>
import { computed, ref } from "vue";

const count = ref(0);

const increment = () => count.value++;
const decrement = () => count.value--;
const reset = () => (count.value = 0);

const message = computed(() => {
  return count.value > 0 ? "Positive" : count.value < 0 ? "Negative" : "Zero";
});
</script>

<template>
  <div>
    <h1>Vue Counter App</h1>
    <h2>{{ count }}</h2>
    <p>
      Status: <strong>{{ message }}</strong>
    </p>
    <div>
      <button @click="increment">Increment</button>
      <button @click="decrement">Decrement</button>
      <button @click="reset">Reset</button>
    </div>
  </div>
</template>
