<script setup>
import { ref } from 'vue';
import Modal from '@/Components/Breeze/Modal.vue';
import ContactForm from '@/Layouts/Partials/ContactForm.vue';
import ContactSuccess from '@/Layouts/Partials/ContactSuccess.vue';

const contactModal = ref(false);
const success = ref(false);
</script>

<template>
  <nav class="max-w-7xl mx-auto py-12 px-8 flex justify-between items-center">
    <!-- Navigation Title -->
    <div>
      <h1 class="text-xl font-bold cursor-pointer">Riley Grotenhuis.</h1>
    </div>

    <!-- Contact Button -->
    <div>
      <button
        class="text-lg py-2 px-4 border border-gray-400 rounded-full bg-transparent transition duration-500 ease-in-out transform hover:bg-white hover:border-gray-500 hover:scale-105 text-white hover:text-gray-800 font-semibold"
        @click.prevent="contactModal = true"
      >
        contact
      </button>
    </div>
  </nav>

  <Modal :show="contactModal" @close="contactModal = false">
    <ContactForm
      v-if="!Boolean(success)"
      @success="success = true"
      @closeModal="contactModal = false"
    />
    <ContactSuccess v-else @goback="success = false" />
  </Modal>
</template>
