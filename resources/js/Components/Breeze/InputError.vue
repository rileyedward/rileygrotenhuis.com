<script setup>
defineProps({
  message: {
    type: String,
  },
});
</script>

<template>
  <div v-show="message" class="mt-1">
    <p class="text-sm text-red-400">
      {{ message }}
    </p>
  </div>
</template>
