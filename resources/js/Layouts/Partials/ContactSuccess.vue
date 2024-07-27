<script setup>
defineEmits(['goback']);
</script>

<template>
  <div class="flex items-center justify-center">
    <div class="text-center p-8 rounded-lg shadow-lg">
      <h1 class="text-2xl font-semibold mb-4">Message Sent!</h1>
      <p class="mb-8">
        Thank you for your message, I will get back to you as soon as possible!
      </p>
      <button
        class="text-lg py-2 px-4 border border-gray-400 rounded-full bg-transparent transition duration-500 ease-in-out transform hover:bg-white hover:border-gray-500 hover:scale-105 text-white hover:text-gray-800 font-semibold"
        @click.prevent="$emit('goback')"
      >
        go back
      </button>
    </div>
  </div>
</template>
