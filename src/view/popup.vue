<template>
  <div
    class="flex flex-col justify-center items-center gap-y-[10px] w-[16rem] h-[16rem] p-[20px]"
  >
    <div
      class="color-box w-[10px] h-[10px] border-[1px] border-black rounded-[0.3px]"
      v-if="sRGBHex"
    ></div>
    <div class="color-text" v-if="sRGBHex">{{ sRGBHex }}</div>
    <button
      @click="() => open()"
      class="bg-cyan-500 p-2 border-2 border-blue-800 rounded-lg"
    >
      Open Eye Dropper
    </button>
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
  box-sizing: border-box;
}
.color-box {
  background-color: v-bind(sRGBHex);
}
</style>
