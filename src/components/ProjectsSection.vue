<template>
  <div class="py-20 bg-gray-800" id="projects">
    <div class="container mx-auto px-4">
      <div class="text-center mb-16 text-3xl">
        <h2 class="font-bold text-3xl">My <span class="text-primary">Projects</span></h2>
        <div class="divider w-24 mx-auto bg-primary h-1 rounded my-4"></div>
        <p class="text-gray-300 max-w-full mx-auto text-base">
          Here you’ll find my latest projects, each demonstrating different challenges and effective solutions.
        </p>
      </div>
      
      <div class="flex flex-wrap justify-center gap-8">
        <div 
          v-for="(project, index) in projects" 
          :key="index" 
          class="card w-full md:w-96 bg-gray-900 shadow-xl hover:shadow-primary/20 transition-all duration-300 hover:-translate-y-2"
          :class="{ 'animate-fadeIn': true }"
          :style="{ animationDelay: index * 0.2 + 's' }"
        >
          <figure class="relative overflow-hidden">
            <img :src="project.image || 'https://cdn.prod.website-files.com/6331c6bbc21f6fa6209a8597/65bb0e1f0e197bb1ea06c74a_E-commerce%20%20%E0%B8%AD%E0%B8%B5%E0%B8%84%E0%B8%AD%E0%B8%A1%E0%B9%80%E0%B8%A1%E0%B8%B4%E0%B8%A3%E0%B9%8C%E0%B8%8B%20%E0%B8%84%E0%B8%B7%E0%B8%AD%E0%B8%AD%E0%B8%B0%E0%B9%84%E0%B8%A3%20%20%E0%B8%A1%E0%B8%B5%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B9%80%E0%B8%A0%E0%B8%97%E0%B8%AD%E0%B8%B0%E0%B9%84%E0%B8%A3%E0%B8%9A%E0%B9%89%E0%B8%B2%E0%B8%87.jpg'" 
                 :alt="project.title" 
                 class="w-full h-64 object-cover transition-transform duration-500 hover:scale-105" />
            <!-- Badge on top of image -->
            <div class="absolute top-4 right-4">
              <div class="badge badge-primary">{{ project.category }}</div>
            </div>
          </figure>
          
          <div class="card-body">
            <h3 class="card-title text-xl relative group">
              {{ project.title }}
              <!-- Animated underline on hover -->
              <span class="absolute -bottom-1 left-0 w-0 h-0.5 bg-primary group-hover:w-full transition-all duration-300"></span>
            </h3>
            
            <p class="text-gray-300 whitespace-pre-line" v-html="formatDescription(project.description)"></p>
            
            <div class="flex flex-wrap gap-2 my-3">
              <div v-for="tech in project.technologies" :key="tech" 
                   class="badge badge-outline hover:badge-primary transition-colors duration-300">
                {{ tech }}
              </div>
            </div>
            
            <div class="card-actions justify-between mt-4">
              <a :href="project.liveLink" class="btn btn-sm btn-primary hover:scale-105 transition-transform duration-300" target="_blank">
                <i class="fas fa-external-link-alt mr-2"></i> Live Demo
              </a>
              <a :href="project.codeLink" class="btn btn-sm btn-ghost hover:bg-gray-800 hover:scale-105 transition-transform duration-300" target="_blank">
                <i class="fab fa-github mr-2"></i> Code
              </a>
            </div>
          </div>
        </div>
      </div>
      
      <div class="text-center mt-16"></div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import Burger from '../assets/ecomBurger.png'
import Petshop from '../assets/ecomPet.png'

const allProjects = [
  {
    title: 'Web applications and line bot for Pet products ',
    category: 'Web App',
     description:
    'Main features:\n' +
    '- Product display: pet food, toys, images, prices\n' +
    '- Shopping cart: add items and place orders\n' +
    '- User login via Line Login (⚠️demo only, no data stored⚠️)\n' +
    '- Admin panel accessible by adding <strong>/admin/products</strong> to URL\n' +
    '- Mobile responsive UI required for smooth usage on all devices',
    technologies: ['Vue.js', 'Tailwind CSS','DaisyiUI', 'Node.js (Nest.js)', 'MongoDB','Mobile Responsive','Vercel','Render'],
    liveLink: 'https://petshop-chi-lilac.vercel.app/',
    codeLink: 'https://github.com/Mosspiy/petshop.git',
    image: Petshop,
    featured: true
  },
  {
  title: 'Website for a Food and Beverage Ordering System',
  category: 'Website',
 description:
  'Main features:\n' +
  '- Product display: name, price, image\n' +
  '- Shopping cart: add items and place orders\n' +
  '- User management: login & register\n' +
  '- Product management: add/edit/delete\n' +
  '- Order management: view & update status\n\n' +
  '🔐 Login with admin@admin.com / 1234 to access Admin Panel',
  technologies: ['Vue.js', 'DaisyUI', 'Tailwind Css','Node.js (Express)', 'PostgreSQL','Vercel','Render'],
  liveLink: 'https://ecommerce-frontend-ten-iota.vercel.app/',
  codeLink: 'https://github.com/Mosspiy/ecommerce_Frontend',
  image: Burger,
  featured: true
},

];

const showAll = ref(false);
const projects = computed(() => {
  return showAll.value ? allProjects : allProjects.filter(p => p.featured);
});

function formatDescription(text) {
  return text.replace(/\n/g, '<br>');
}
</script>