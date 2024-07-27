<script setup>
import { useForm } from '@inertiajs/vue3';
import InputError from '@/Components/Breeze/InputError.vue';
import { computed } from 'vue';

const form = useForm({
  first_name: '',
  last_name: '',
  email: '',
  subject: '',
  message: '',
});

const formIsValid = computed(() => {
  const requiredFields =
    form.first_name &&
    form.last_name &&
    form.email &&
    form.subject &&
    form.message;

  return requiredFields && !Boolean(form.processing);
});

const submitForm = () => {
  alert('Todo...');
};
</script>

<template>
  <div>
    <h3 class="text-xl text-gray-50 font-bold mb-2">Get in touch.</h3>

    <p class="text-sm mb-4">
      I’d love to hear from you! Whether you have a question, a project idea, or
      just want to connect, feel free to reach out. Fill out the form below, and
      I’ll get back to you as soon as possible.
    </p>

    <form class="w-full space-y-6">
      <div class="w-full flex items-center gap-4">
        <!-- First Name -->
        <div class="w-full">
          <label
            for="first_name"
            class="block text-sm font-medium text-gray-300"
          >
            First Name
          </label>
          <input
            v-model="form.first_name"
            type="text"
            id="first_name"
            class="mt-1 block w-full px-3 py-2 bg-neutral-800 text-gray-300 border border-gray-600 rounded-md shadow-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
          />
          <InputError :message="form.errors.first_name" />
        </div>

        <!-- Last Name -->
        <div class="w-full">
          <label
            for="last_name"
            class="block text-sm font-medium text-gray-300"
          >
            Last Name
          </label>
          <input
            v-model="form.last_name"
            type="text"
            id="last_name"
            class="mt-1 block w-full px-3 py-2 bg-neutral-800 text-gray-300 border border-gray-600 rounded-md shadow-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
          />
          <InputError :message="form.errors.last_name" />
        </div>
      </div>

      <div class="w-full flex items-center gap-4">
        <!-- Email -->
        <div class="w-full">
          <label for="email" class="block text-sm font-medium text-gray-300">
            Email
          </label>
          <input
            v-model="form.email"
            type="text"
            id="email"
            class="mt-1 block w-full px-3 py-2 bg-neutral-800 text-gray-300 border border-gray-600 rounded-md shadow-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
          />
          <InputError :message="form.errors.email" />
        </div>

        <!-- Subject -->
        <div class="w-full">
          <label for="subject" class="block text-sm font-medium text-gray-300">
            Subject
          </label>
          <input
            v-model="form.subject"
            type="text"
            id="subject"
            class="mt-1 block w-full px-3 py-2 bg-neutral-800 text-gray-300 border border-gray-600 rounded-md shadow-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
          />
          <InputError :message="form.errors.subject" />
        </div>
      </div>

      <div class="w-full flex items-center gap-4">
        <!-- Message -->
        <div class="w-full">
          <label for="message" class="block text-sm font-medium text-gray-300">
            Message
          </label>
          <textarea
            v-model="form.message"
            id="message"
            rows="4"
            class="mt-1 block w-full px-3 py-2 bg-neutral-800 text-gray-300 border border-gray-600 rounded-md shadow-sm focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
          />
          <InputError :message="form.errors.message" />
        </div>
      </div>

      <!-- Submit Button -->
      <div class="flex justify-end">
        <button
          class="py-2 px-4 border border-gray-400 rounded-full transition duration-500 ease-in-out transform hover:scale-105 text-base font-semibold"
          :class="{
            'bg-white hover:bg-transparent hover:border-gray-500 text-gray-800 hover:text-white':
              Boolean(formIsValid),
            'bg-gray-500 text-gray-400': !Boolean(formIsValid),
          }"
          :disabled="!formIsValid"
          @click.prevent="submitForm"
        >
          Send message
        </button>
      </div>
    </form>
  </div>
</template>
