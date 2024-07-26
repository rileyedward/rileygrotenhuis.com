<script setup>
/** Scrolls the user back to the top of the page */
const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth',
  });
};

/** Opens the contact modal form */
const openContactModal = () => {
  alert('TODO');
};
</script>

<template>
  <nav class="max-w-7xl mx-auto py-12 px-8 flex justify-between items-center">
    <!-- Navigation Title -->
    <div>
      <h1 class="text-xl font-bold cursor-pointer" @click.prevent="scrollToTop">
        Riley Grotenhuis.
      </h1>
    </div>

    <!-- Contact Button -->
    <div>
      <button
        class="text-lg py-2 px-4 border border-gray-400 rounded-full bg-transparent transition duration-500 ease-in-out transform hover:bg-white hover:border-gray-500 hover:scale-105 text-white hover:text-gray-800"
        @click.prevent="openContactModal"
      >
        contact
      </button>
    </div>
  </nav>
</template>
