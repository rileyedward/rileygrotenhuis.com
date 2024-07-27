<script setup>
import GitHubIcon from '@/Components/Icons/GitHubIcon.vue';
import LinkedInIcon from '@/Components/Icons/LinkedInIcon.vue';
</script>

<template>
  <footer
    class="max-w-7xl mx-auto px-8 py-24 flex flex-col md:flex-row gap-4 text-center md:text-left justify-between items-center"
  >
    <div>
      <h3 class="text-xl font-semibold">Riley Grotenhuis.</h3>
      <p class="text-base font-semibold">&copy; 2024. All rights reserved.</p>
    </div>

    <div class="flex items-center gap-4">
      <a href="https://github.com/rileyedward" target="_blank">
        <GitHubIcon />
      </a>

      <a href="https://linkedin.com/in/rileygrotenhuis" target="_blank">
        <LinkedInIcon />
      </a>

      <a
        href="mailto:rileyedwardgrotenhuis@gmail.com"
        class="text-lg py-2 px-4 border border-gray-400 rounded-full bg-transparent transition duration-500 ease-in-out transform hover:bg-white hover:border-gray-500 hover:scale-105 text-white hover:text-gray-800 font-semibold"
      >
        contact
      </a>
    </div>
  </footer>
</template>
