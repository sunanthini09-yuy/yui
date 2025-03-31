<template>
  <div class="flex flex-col items-center justify-center h-screen bg-gradient-to-b from-pink-300 to-pink-400 p-4">
    <div class="bg-white p-8 rounded-3xl shadow-xl text-center w-full max-w-md relative overflow-hidden">
      <h1 class="text-4xl font-extrabold text-pink-600 drop-shadow-lg">🎉 ยินดีด้วย! 🎉</h1>
      <p class="text-lg text-gray-700 mt-3 font-medium">ตอนนี้เราเป็นแฟนกันแล้วนะ! 💑</p>
      
      <div class="mt-6 flex flex-col gap-4 items-center">
        <img src="https://source.unsplash.com/200x200/?love,heart" alt="love" class="https://pin.it/4oPqoAfmv" />
        <p class="text-xl text-pink-600 font-semibold">ฉันรักเธอมากนะ ❤️</p>
      </div>
      
      <button
        class="mt-6 px-8 py-3 bg-blue-500 text-white font-bold rounded-full shadow-lg hover:bg-blue-700 transition-transform transform hover:scale-110"
        @click="goHome"
      >
        กลับไปหน้าแรก 🏡
      </button>
    </div>
  </div>
</template>

<script setup>
import { useRouter } from "vue-router";
const router = useRouter();

const goHome = () => {
  router.push("/");
};
</script>

<style>
body {
  font-family: "Prompt", sans-serif;
}
</style>