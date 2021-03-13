<template>
  <div class="container mx-auto px-4">
    <div
      class="mt-10 px-8 grid gap-8 grid-cols-1 md:grid-cols-2 md:px-10 lg:px-16 xl:px-16 py-16 mx-auto bg-indigo-50 text-gray-900 shadow-2xl"
    >
      <div class="flex flex-col justify-between">
        <div>
          <h2 class="text-4xl lg:text-5xl font-bold leading-tight">
            {{ this.contact.title }}
          </h2>
          <p class="text-gray-700 mt-8 text-lg">
            {{ this.contact.description }}
          </p>
        </div>
      </div>
      <div class="">
        <div>
          <span class="uppercase text-sm text-gray-600 font-bold"
            >{{ this.contact.name }}</span
          >
          <input
            class="w-full bg-gray-200 text-gray-900 mt-2 p-3 rounded-lg focus:outline-none focus:shadow-outline"
            type="text"
            placeholder=""
          />
        </div>
        <div class="mt-8">
          <span class="uppercase text-sm text-gray-600 font-bold">{{ this.contact.email }}</span>
          <input
            class="w-full bg-gray-200 text-gray-900 mt-2 p-3 rounded-lg focus:outline-none focus:shadow-outline"
            type="text"
          />
        </div>
        <div class="mt-8">
          <span class="uppercase text-sm text-gray-600 font-bold">{{ this.contact.message }}</span>
          <textarea
            class="w-full h-32 bg-gray-200 text-gray-900 mt-2 p-3 rounded-lg focus:outline-none focus:shadow-outline"
          ></textarea>
        </div>
        <div class="mt-8">
          <button
            class="transition duration-300 ease-in-out uppercase text-sm font-bold tracking-wide bg-indigo-500 hover:bg-indigo-600 text-gray-100 p-3 rounded-lg w-full focus:outline-none focus:shadow-outline"
          >
            {{ this.contact.send }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import axios from "axios";

export default {
  components: {},
  data() {
    return {
      error: null,
      contact: [],
    };
  },
  async mounted() {
    try {
      const response = await axios.get("https://nuxt-strapi-cms.herokuapp.com/contact");
      this.contact = response.data;
    } catch (error) {
      this.error = error;
    }
  }
};
</script>

<style scoped></style>
