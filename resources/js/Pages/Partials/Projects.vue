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
  },
  {
    title: 'Applicy',
    href: 'https://github.com/rileyedward/applicy',
    slogan: 'Streamline your job application journey',
    tech: 'PHP, Laravel, MySQL, JavaScript, Vue.js, TailwindCSS, Docker, OpenAI, AI',
    description: [
      'Applicy is a comprehensive online platform that simplifies your job application process. Create a personalized profile to seamlessly track all your job applications and monitor their progress in real time. With Applicy, you can easily organize your job search efforts, making it simpler to stay on top of your applications and secure your next opportunity.'
    ]
  },
  {
    title: 'AirQueue',
    href: 'https://github.com/rileyedward/airqueue',
    slogan: 'Share music with your friends using Live Sessions!',
    tech: 'PHP, Laravel, MySQL, JavaScript, Vue.js, TailwindCSS, Docker',
    description: [
      'AirQueue is a platform designed to enhance your music-sharing experience with friends through interactive Live Sessions. With AirQueue, you can:',
      'Start or Join Live Sessions: Create a new session or join an existing one to share and discover music in real time.',
      'Request Songs: Suggest songs to be played during the session and share your musical taste with others.',
      'Manage Song Requests: View and manage incoming song requests from other participants and seamlessly add them to your Spotify player queue.'
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
        <p class="text-gray-400 mb-6">
          {{ projects[focusedProject].tech }}
        </p>

        <!-- Description -->
        <div class="space-y-3">
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
  </div>
</template>
