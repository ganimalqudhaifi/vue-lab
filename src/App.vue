<script setup lang="ts">
import ParentComponent from "./components/ParentComponent.vue";
import VueCounterApp from "./components/VueCounterApp.vue";
import VueTemplateRefDemo from "./components/VueTemplateRefDemo.vue";
import VueTransitionExample from "./components/VueTransitionExample.vue";
import VueWatchersDemo from "./components/VueWatchersDemo.vue";
</script>

<template>
  <VueCounterApp />
  <div class="w-full border my-4"></div>
  <VueWatchersDemo />
  <div class="w-full border my-4"></div>
  <VueTemplateRefDemo />
  <div class="w-full border my-4"></div>
  <ParentComponent />
  <div class="w-full border my-4"></div>
  <VueTransitionExample />
</template>
