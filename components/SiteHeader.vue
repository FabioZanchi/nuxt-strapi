<template>
  <div class="inline-flex justify-between p-8 w-full item-center">
    <img src="~/assets/images/logo.png" alt="Logo" class="w-40 h-auto" />
    <ul class="inline-flex">
      <li class="py-3">
        <nuxt-link
          class="p-3 rounded hover:bg-indigo-100 transition duration-300 ease-in-out"
          to="/"
          >Home</nuxt-link
        >
      </li>
      <li class="py-3">
        <nuxt-link
          class="p-3 rounded hover:bg-indigo-100 transition duration-300 ease-in-out"
          to="/contact"
          >Contact Us</nuxt-link
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {};
</script>

<style></style>
