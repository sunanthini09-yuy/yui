<template>
  <div class="flex flex-col items-center justify-center h-screen bg-gradient-to-b from-pink-200 to-pink-300 p-4">
    <div class="bg-white p-8 rounded-3xl shadow-xl text-center w-full max-w-md relative overflow-hidden">
      <h1 class="text-4xl font-extrabold text-pink-600 drop-shadow-lg animate-bounce">💖 เธอคะ!? 💖</h1>
      <p class="text-lg text-gray-700 mt-3 font-medium">เป็นแฟนกับเค้าไหม? 🥺</p>
      
      <div class="mt-6 flex gap-6 justify-center relative">
        <NuxtLink to="/next-page" class="px-8 py-3 bg-green-500 text-white font-bold rounded-full shadow-lg hover:bg-green-700 transition-transform transform hover:scale-110">
            ใช่ 💘
        </NuxtLink>


        <button
          ref="noButton"
          class="px-8 py-3 bg-red-500 text-white font-bold rounded-full shadow-lg transition-transform transform"
          @mouseover="moveNoButton"
        >
          ไม่ ❌
        </button>
      </div>

      <transition name="fade">
        <p v-if="showMessage" class="mt-6 text-2xl text-pink-600 font-bold animate-pulse">เย้! ฉันรักเธอนะ ❤️</p>
      </transition>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const showMessage = ref(false);
const noButton = ref(null);
const router = useRouter();

const goToNextPage = () => {
  router.push("/next-page");
};

const moveNoButton = () => {
  if (noButton.value) {
    const x = Math.random() * 300 - 150; // ขยับมากขึ้น -150px ถึง 150px
    const y = Math.random() * 300 - 150;
    noButton.value.style.transform = `translate(${x}px, ${y}px)`;
    noButton.value.style.transition = "transform 0.2s ease-in-out"; // ทำให้ขยับลื่นขึ้น
  }
};
</script>

<style>
body {
  font-family: "Prompt", sans-serif;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
}
</style>
