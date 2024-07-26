<script setup>
import Navbar from '@/Layouts/Partials/Navbar.vue';
</script>

<template>
  <div>
    <Navbar />

    <main>
      <slot />
    </main>
  </div>
</template>
