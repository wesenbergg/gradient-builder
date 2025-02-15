<script setup lang="ts">
import { ref } from "vue";
import logo from "@/assets/logo.jpeg";

defineProps<{ msg: string }>();

const aspectRatio = ref("aspect-1-1");
</script>

<template>
  <main
    :class="['flex items-center space-x-16 justify-center text-cyan-900 bg-cyan-50 dark:text-cyan-50! dark:bg-cyan-900!']">
    <section class="hidden sm:block space-y-4">
      <div :class="[
        'border-2 border-cyan-950/15 shadow-xl flex flex-col items-center justify-center bg-gray-500 rounded-xl h-[50dvh]',
        'gradient',
        aspectRatio,
      ]">
      </div>
      <div class="space-x-4">
        <button class="border border-cyan-800 px-4 py-2 rounded-md" @click="() => (aspectRatio = 'aspect-1-1')">
          1:1
        </button>
        <button class="border border-cyan-800 px-4 py-2 rounded-md" @click="() => (aspectRatio = 'aspect-3-4')">
          3:4
        </button>
      </div>
    </section>
    <section class="grid content-center min-h-dvh space-y-8 max-sm:pl-4">
      <div class="max-w-[100vw]">
        <img :src="logo" alt="Logo" class="w-32 h-32 mb-8 rounded-2xl" width="64px" height="64px" />

        <h1 class="text-4xl text-cyan-950 dark:text-cyan-50 font-bold">{{ msg }}</h1>
        <p class="mb-8 text-cyan-950/80 dark:text-cyan-50/85">Select up to 5 colors.</p>

        <div class=" w-full sm:w-md relative scroll-container">
          <div class="grid grid-cols-5 gap-32 text-center *:pt-[18px] overflow-auto">
            <span class="w-24 h-24 mb-8 rounded-2xl bg-amber-500"></span>
            <span class="inactive-color-picker">+</span>
            <span class="inactive-color-picker">+</span>
            <span class="inactive-color-picker">+</span>
            <span class="inactive-color-picker">+</span>
          </div>
        </div>
      </div>
      <div class="flex items-end space-x-4">
        <button type="button" class="button">
          Copy CSS</button>
        <button type="button" class="button">
          Download as Image</button>
      </div>
    </section>
  </main>
</template>

<style scoped>
.unstyled {
  appearance: none;
  border: none;
  cursor: pointer;
  -webkit-appearance: none;
}

/* add styles */
.aspect-1-1 {
  aspect-ratio: 1/1 !important;
}

.aspect-3-4 {
  aspect-ratio: 3/4;
}

.gradient {
  background-image: linear-gradient(45deg,
      hsl(0deg 0% 100%) 0%,
      hsl(308deg 75% 93%) 1%,
      hsl(307deg 71% 86%) 4%,
      hsl(306deg 69% 79%) 12%,
      hsl(307deg 71% 86%) 16%,
      hsl(308deg 75% 93%) 29%,
      hsl(0deg 0% 100%) 52%,
      hsl(190deg 74% 95%) 72%,
      hsl(190deg 74% 91%) 85%,
      hsl(190deg 75% 86%) 92%,
      hsl(190deg 74% 91%) 96%,
      hsl(190deg 74% 95%) 99%,
      hsl(0deg 0% 100%) 100%);
}

.scroll-container {
  position: relative;
}

.scroll-container::after {
  content: '';
  position: absolute;
  top: 0;
  right: 0;
  width: 1.5rem;
  height: 100%;
  background: linear-gradient(to left, var(--color-cyan-50), rgba(255, 255, 255, 0));
  z-index: 10;
}

.dark .scroll-container::after {
  background: linear-gradient(to left, var(--color-cyan-900), rgba(0, 0, 0, 0));
}
</style>
