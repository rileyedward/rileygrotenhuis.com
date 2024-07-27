<script setup>
import GitHubIcon from '@/Components/Icons/GitHubIcon.vue';
import LinkedInIcon from '@/Components/Icons/LinkedInIcon.vue';
</script>

<template>
  <div
    class="max-w-6xl mx-auto py-8 md:py-24 px-8 flex flex-col-reverse md:flex-row gap-8 md:gap-0 justify-between items-center"
  >
    <!-- Hero Bio -->
    <div class="max-w-[550px]">
      <div class="text-base font-bold text-gray-400 mb-4">
        Software Engineer based in Kansas City
      </div>

      <div class="mb-8">
        <h1 class="text-3xl font-bold mb-2">Hi, I'm Riley!</h1>
        <p class="text-3xl font-bold">
          I've been building high performing web applications for 4 years.
        </p>
      </div>

      <div class="flex flex-row-reverse md:flex-row items-center gap-4">
        <a
          href="https://dev.to/rileygrotenhuis"
          target="_blank"
          class="py-2 px-4 border border-gray-400 rounded-full bg-white transition duration-500 ease-in-out transform hover:bg-transparent hover:border-gray-500 hover:scale-105 text-base text-gray-800 hover:text-white font-semibold"
        >
          read my blog
        </a>

        <a href="https://github.com/rileyedward" target="_blank">
          <GitHubIcon />
        </a>

        <a href="https://linkedin.com/in/rileygrotenhuis" target="_blank">
          <LinkedInIcon />
        </a>
      </div>
    </div>

    <!-- Hero Image -->
    <div class="w-full flex justify-center items-center">
      <img
        src="/images/Profile.jpg"
        alt="Profile"
        class="w-[325px] h-[325px] bg-gray-200 rounded-full"
      />
    </div>
  </div>
</template>
