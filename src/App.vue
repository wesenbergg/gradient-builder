<script setup lang="ts">
import { ref } from "vue";
import MainLayout from "./components/MainLayout.vue";

const isDarkMode = ref(false);

const toggleDarkMode = () => {
  isDarkMode.value = !isDarkMode.value;
  document.documentElement.classList.toggle('dark', isDarkMode.value);
};

const showDialog = () => {
  document.querySelector('dialog')?.showModal();
};
</script>

<template>
  <dialog class="backdrop:w-dvh backdrop:h-dvh backdrop:bg-cyan-900/50 backdrop:dark:bg-cyan-900/80 m-auto bg-white/0">
    <form method="dialog" class="p-8 bg-cyan-50 dark:bg-cyan-900 rounded-xl shadow-xl relative">
      <h2 class="text-2xl font-bold">Dialog</h2>
      <p class="mb-4">This is a dialog.</p>
      <button autofocus title="Close"
        class="absolute top-2 right-2 font-mono bg-cyan-900/10 w-8 h-8 rounded-full">x</button>
      <p>This modal dialog has a groovy backdrop!</p>
    </form>
  </dialog>
  <button @click="toggleDarkMode"
    class="absolute top-4 right-4 w-12 h-12 text-2xl bg-cyan-500/60 text-black font-bold rounded-full hover:bg-cyan-500/80 transition-colors">
    {{ isDarkMode ? '🌝' : '🌚' }}
  </button>
  <button @click="showDialog"
    class="absolute bottom-4 right-4 w-12 h-12 text-2xl bg-cyan-300 text-black font-bold rounded-full  transition-colors">
    =
  </button>
  <MainLayout msg="Gradient builder" />
</template>

<style scoped>
/* Add styles */
</style>