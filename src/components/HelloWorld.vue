<script setup lang="ts">
import { ref } from 'vue'
import logo from '@/assets/logo.jpeg'

defineProps<{ msg: string }>()

const count = ref(0)
</script>

<template>
  <div class="flex flex-col items-center justify-center min-h-screen bg-gray-100">
    <img :src="logo" alt="Logo" class="w-32 h-32 mb-8 rounded-2xl" />
    
    <h1 class="text-4xl font-bold text-gray-800 mb-8">{{ msg }}</h1>

    <div class="bg-white rounded-lg shadow-md p-8">
      <button 
        type="button" 
        @click="count++" 
        class="px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600 transition-colors"
      >
        count is {{ count }}
      </button>
      
      <p class="mt-4 text-gray-600">
        Edit
        <code class="bg-gray-100 px-2 py-1 rounded">components/HelloWorld.vue</code> 
        to test HMR
      </p>
    </div>
  </div>
</template>

<style scoped>
/* add styles */
</style>
