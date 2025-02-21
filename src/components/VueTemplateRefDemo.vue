<template>
  <div>
    <h1>Vue 3 useTemplateRef Demo</h1>
    <input ref="my-input" type="text" placeholder="Type here..." />
  </div>
</template>

<script>
import { onMounted, useTemplateRef } from "vue";

export default {
  setup() {
    const input = useTemplateRef("my-input");

    onMounted(() => {
      input.value.focus();
    });

    return { input };
  },
};
</script>
