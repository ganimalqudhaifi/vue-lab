<template>
  <div>
    <p>{{ msg }}</p>
    <button @click="$emit('custom-event', 'Hello from Child!')">
      Click Me
    </button>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from "vue";

const props = defineProps({
  msg: String,
});

const emit = defineEmits(["custom-event"]);

// const emitEvent = () => {
//   emit("custom-event", "Hello from Child!");
// };
</script>
