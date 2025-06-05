<template>
  <div class="py-20 bg-gray-900" id="skills">
    <div class="container mx-auto px-4">
      <div class="text-center mb-16 text-3xl">
        <h2 class="text-3xl font-bold text-white">My <span class="text-primary">Skills</span></h2>
        <div class="divider w-24 mx-auto bg-primary h-1 rounded my-4"></div>
        <p class="text-gray-300 max-w-full mx-auto text-base">
          I've worked with a variety of technologies and frameworks, allowing me to build complete solutions from frontend to backend.
        </p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mt-12">
        <div v-for="(category, index) in skillCategories" :key="index" class="animate">
          <div class="card bg-gray-800 shadow-xl">
            <div class="card-body">
              <h3 class="card-title text-xl font-bold mb-4 text-white">
                <i :class="category.icon" class="mr-2 text-primary"></i>
                {{ category.name }}
              </h3>
              <div class="grid grid-cols-3 gap-4">
                <div v-for="skill in category.skills" :key="skill.name" class="skill-item">
                  <div class="logo-container bg-gray-700 p-3 rounded-xl w-16 h-16 flex items-center justify-center mx-auto">
                    <img :src="skill.logo" :alt="`${skill.name} logo`" class="w-10 h-10 object-contain" />
                  </div>
                  <span class="skill-name text-gray-300 text-sm text-center block mt-2">{{ skill.name }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const skillCategories = ref([
  {
    name: 'Frontend',
    icon: 'fas fa-code',
    skills: [
      { 
        name: 'HTML',
        logo: 'https://www.svgrepo.com/show/452228/html-5.svg'
      },
      { 
        name: 'CSS',
        logo: 'https://www.svgrepo.com/show/452185/css-3.svg'
      },
      { 
        name: 'JavaScript',
        logo: 'https://www.svgrepo.com/show/349419/javascript.svg'
      },
      { 
        name: 'Vue.js',
        logo: 'https://www.svgrepo.com/show/354528/vue.svg'
      },
      { 
        name: 'Tailwind',
        logo: 'https://www.svgrepo.com/show/374118/tailwind.svg'
      },
      { 
        name: 'DaisyUI',
        logo: 'https://img.daisyui.com/images/daisyui/mark-static.svg'
      },
      { 
        name: 'Responsive',
        logo: 'https://www.svgrepo.com/show/469630/responsive.svg'
      }
    ]
  },
  {
    name: 'Backend',
    icon: 'fas fa-server',
    skills: [
      { 
        name: 'Node.Js',
        logo: 'https://www.svgrepo.com/show/378837/node.svg'
      },
      { 
        name: 'Express.Js',
        logo: 'https://img.icons8.com/?size=100&id=kg46nzoJrmTR&format=png&color=000000'
      },
      {
        name: 'Nest.Js',
        logo: 'https://www.svgrepo.com/show/354107/nestjs.svg'
      },
      {
        name: 'TypeScript',
        logo: 'https://www.svgrepo.com/show/349540/typescript.svg'
      },
      { 
        name: 'REST APIs',
        logo: 'https://www.svgrepo.com/show/336153/api.svg'
      },
      { 
        name: 'MongoDB',
        logo: 'https://www.svgrepo.com/show/373845/mongo.svg'
      },
      { 
        name: 'PostgreSQL',
        logo: 'https://www.svgrepo.com/show/354200/postgresql.svg'
      },
      { 
        name: 'Python',
        logo: 'https://www.svgrepo.com/show/452091/python.svg'
      }
    ]
  },
  {
    name: 'Tools & Others',
    icon: 'fas fa-toolbox',
    skills: [
      { 
        name: 'Git',
        logo: 'https://www.svgrepo.com/show/452210/git.svg'
      },
      { 
        name: 'Docker',
        logo: 'https://www.svgrepo.com/show/452192/docker.svg'
      },
      { 
        name: 'Figma',
        logo: 'https://www.svgrepo.com/show/448222/figma.svg'
      },
      {
        name: 'AWS',
        logo: 'https://www.svgrepo.com/show/376356/aws.svg'
      }
    ]
  }
]);
</script>

<style scoped>
.skill-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 1rem;
}

.logo-container {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.logo-container:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
}

.animate {
  animation: fadeIn 0.5s ease-in-out;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>