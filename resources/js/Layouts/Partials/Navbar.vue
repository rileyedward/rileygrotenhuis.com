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
        class="py-2 px-4 border border-gray-400 rounded-full transition duration-500 ease-in-out transform hover:bg-gray-400 hover:scale-105"
        @click.prevent="openContactModal"
      >
        <span class="text-base text-white hover:text-gray-100"> contact </span>
      </button>
    </div>
  </nav>
</template>
