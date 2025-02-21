<template>
  <div>
    <h1>Vue 3 Watchers Demo</h1>
    <input v-model="count" type="number" />
    <p>Count: {{ count }}</p>
    <p>Double Count: {{ doubleCount }}</p>
  </div>
</template>

<script>
import { ref, computed, watch, watchEffect, nextTick } from "vue";

export default {
  setup() {
    const count = ref(0);
    const doubleCount = computed(() => count.value * 2);

    // Basic watch
    watch(count, (newValue, oldValue) => {
      console.log(`Count changed from ${oldValue} to ${newValue}`);
    });

    // watchEffect (runs immediately)
    watchEffect(() => {
      console.log(`watchEffect: Count is now ${count.value}`);
    });

    // Post watcher (runs after Vue updates the DOM)
    watch(
      count,
      async () => {
        await nextTick();
        console.log(`Post Watcher: DOM updated, count is now ${count.value}`);
      },
      { flush: "post" }
    );

    // Sync watcher (runs before Vue updates the DOM)
    watch(
      count,
      (newValue) => {
        console.log(`Sync Watcher: Count is about to change to ${newValue}`);
      },
      { flush: "sync" }
    );

    return { count, doubleCount };
  },
};
</script>
