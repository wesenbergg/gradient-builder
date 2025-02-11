<script setup lang="ts">
import { ref } from "vue";
import MainLayout from "./components/MainLayout.vue";

const isDarkMode = ref(false);

const toggleDarkMode = () => {
  isDarkMode.value = !isDarkMode.value;
  document.documentElement.classList.toggle('dark', isDarkMode.value);
};
</script>

<template>
  <button @click="toggleDarkMode"
    class="absolute top-4 right-4 w-12 h-12 text-2xl bg-cyan-500/60 text-black font-bold rounded-full hover:bg-cyan-500/80 transition-colors">
    {{ isDarkMode ? '🌝' : '🌚' }}
  </button>
  <MainLayout msg="Gradient builder" />
</template>

<style scoped>
/* Add styles */
</style>