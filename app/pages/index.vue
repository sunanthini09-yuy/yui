<template>
  <div class="flex flex-col items-center justify-center h-screen bg-pink-100 p-4">
    <div class="bg-white p-6 rounded-2xl shadow-lg text-center w-full max-w-md">
      <h1 class="text-3xl font-bold text-pink-600">💖 เอิ่มมมม 💖</h1>
      <p class="text-lg text-gray-700 mt-2">คุณจะเป็นแฟนกับฉันไหม? 🥺</p>

      <div class="mt-6 flex gap-4 justify-center relative">
        <button
          class="px-6 py-2 bg-green-500 text-white font-semibold rounded-full shadow-md hover:bg-green-700 transition"
          @click="sayYes"
        >
          ใช่ 💘
        </button>

        <button
          ref="noButton"
          class="px-6 py-2 bg-red-500 text-white font-semibold rounded-full shadow-md transition"
          @mouseover="moveNoButton"
        >
          ไม่ ❌
        </button>
      </div>

      <p v-if="showMessage" class="mt-4 text-xl text-pink-500 font-semibold">
        เย้! ฉันรักเธอนะ ❤️
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const showMessage = ref(false);
const noButton = ref(null);

const sayYes = () => {
  showMessage.value = true;
};

const moveNoButton = () => {
  if (noButton.value) {
    const x = Math.random() * 200 - 100; // ขยับในช่วง -100px ถึง 100px
    const y = Math.random() * 200 - 100;
    noButton.value.style.transform = `translate(${x}px, ${y}px)`;
  }
};
</script>

<style>
body {
  font-family: "Prompt", sans-serif;
}
</style>
