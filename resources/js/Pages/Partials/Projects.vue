<script setup>
import GitHubIcon from '@/Components/Icons/GitHubIcon.vue';
import { ref } from 'vue';

const projects = ref([
  {
    title: 'Corvesive',
    href: 'https://github.com/rileyedward/corvesive',
    slogan: 'Simplify your budgeting',
    tech: 'PHP, Laravel, MySQL, JavaScript, Vue.js, TailwindCSS, Docker',
    description: [
      'Corvesive is an online application designed to simplify your budgeting. Track your income by uploading pay stubs, record your monthly expenses, and effortlessly monitor where your money is going and how much you have left. Gain clarity on your financial situation to make better budgeting decisions.'
    ]
  }
]);

const focusedProject = ref(0);
</script>

<template>
  <div class="w-full py-24">
    <div class="max-w-6xl mx-auto px-8">
      <!-- Project -->
      <div>
        <div class="flex items-center justify-between mb-2">
          <!-- Details -->
          <div>
            <a :href="projects[focusedProject].href" target="_blank">
              <h3 class="text-4xl font-extrabold text-red-500">
                {{ projects[focusedProject].title }}
              </h3>
            </a>
            <p class="text-lg text-gray-300">
              {{ projects[focusedProject].slogan }}
            </p>
          </div>

          <a :href="projects[focusedProject].href" target="_blank">
            <GitHubIcon />
          </a>
        </div>

        <!-- Technology -->
        <p class="text-gray-400 mb-4">
          {{ projects[focusedProject].tech }}
        </p>

        <!-- Description -->
        <p
          v-for="(paragraph, index) in projects[focusedProject].description"
          :key="index"
          class="text-gray-100"
        >
          {{ paragraph }}
        </p>
      </div>
    </div>
  </div>
</template>
