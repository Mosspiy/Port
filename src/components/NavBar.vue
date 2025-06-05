<template>
  <nav class="fixed top-0 w-full z-50 bg-gray-900 bg-opacity-80 backdrop-blur-lg shadow-sm">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-16">
        <!-- Left: Logo & Mobile Menu -->
        <div class="flex items-center">
          <a href="#" class="text-xl text-primary font-mono font-bold tracking-tight hover:opacity-90">&lt;/PIY&gt;</a>
          <!-- Mobile Menu -->
          <div class="ml-3 lg:hidden">
            <button @click="menuOpen = !menuOpen" class="text-gray-300 focus:outline-none">
              <i class="fas fa-bars text-xl"></i>
            </button>
          </div>
        </div>

        <!-- Right: Navigation -->
        <div class="hidden lg:flex items-center space-x-6">
          <a v-for="item in navItems" :key="item.link" :href="item.link"
            class="text-gray-300 hover:text-primary transition-colors duration-200 font-medium">
            {{ item.name }}
          </a>
          <a href="#contact"
            class="ml-4 bg-primary text-white py-1.5 px-4 rounded-md font-semibold text-sm hover:opacity-90 transition">
            Let’s Connect
          </a>
        </div>
      </div>

      <!-- Mobile Dropdown -->
      <div v-if="menuOpen" class="lg:hidden mt-2">
        <div class="bg-gray-800 rounded-md shadow-md p-3 space-y-2">
          <a v-for="item in navItems" :key="item.link" :href="item.link"
            class="block text-gray-200 hover:text-primary transition">
            {{ item.name }}
          </a>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue';

const menuOpen = ref(false);
const navItems = ref([
  { name: 'Home', link: '#home' },
  { name: 'About', link: '#about' },
  { name: 'Skills', link: '#skills' },
  { name: 'Projects', link: '#projects' },
]);
</script>