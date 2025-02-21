<template>
  <div>
    <h1>Vue Props & Events Demo</h1>
    <ChildComponent msg="Hello from Parent!" @custom-event="handleEvent" />
  </div>
</template>

<script setup>
import ChildComponent from "./ChildComponent.vue";

const handleEvent = (payload) => {
  console.log("Event received from child:", payload);
};
</script>
