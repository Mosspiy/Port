<template>
  <footer class="bg-gray-800 py-8">
    <div class="container mx-auto px-4">
      <div class="flex flex-col md:flex-row justify-between items-center">
        <div class="mb-4 md:mb-0">
          <a href="#" class="text-2xl font-bold text-primary">&lt;/PIY&gt;</a>
          <p class="text-gray-400 mt-2">Web Developer & Designer</p>
        </div>
        
        <div class="flex flex-col items-center md:items-end">
          <p class="text-gray-400">© {{ currentYear }} Piyawat Chotworaanon. All rights reserved.</p>
          <div class="flex gap-4 mt-3">
            <a href="#home" class="text-gray-400 hover:text-primary transition-colors">Home</a>
            <a href="#about" class="text-gray-400 hover:text-primary transition-colors">About</a>
            <a href="#projects" class="text-gray-400 hover:text-primary transition-colors">Projects</a>
            <a href="#contact" class="text-gray-400 hover:text-primary transition-colors">Contact</a>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { computed } from 'vue';

const currentYear = computed(() => new Date().getFullYear());
</script>