<template>
  <div class="main_app">
    <div class="color-box" v-if="sRGBHex"></div>
    <div class="color-text" v-if="sRGBHex">{{ sRGBHex }}</div>
    <button @click="() => open()">Open Eye Dropper</button>
  </div>
</template>

<script>
export default {
  name: "popupView",
};
</script>

<script setup>
import { useEyeDropper } from "@vueuse/core";

const { open, sRGBHex } = useEyeDropper();
</script>

<style>
* {
  font-size: 14px;
}

.main_app {
  display: flex;
  flex-direction: column;
  row-gap: 10px;
  justify-content: center;
  align-items: center;
  width: 200px;
  height: 200px;
  padding: 20px;
}
.color-box {
  background-color: v-bind(sRGBHex);
  width: 10px;
  height: 10px;
  border: solid 1px #000000;
  border-radius: 0.3px;
}
</style>
