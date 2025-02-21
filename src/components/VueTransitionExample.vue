<template>
  <div>
    <h1>Vue Transition Example</h1>
    <button @click="toggle">Toggle Box</button>
    <Transition name="fade" mode="out-in" appear>
      <div v-if="show" class="box" key="box"></div>
    </Transition>
  </div>
</template>

<script setup>
import { ref } from "vue";

const show = ref(false);
const toggle = () => {
  show.value = !show.value;
};
</script>

<style>
.box {
  width: 100px;
  height: 100px;
  background-color: #42b983;
  margin-top: 20px;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s, transform 0.5s;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(-20px);
}
</style>
