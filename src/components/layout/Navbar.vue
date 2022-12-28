<script setup>
import { RouterLink } from "vue-router";
import logoVue from "./logo.vue";
import AuthButton from "./AuthButton.vue";
import NavigationLinksVue from "./NavigationLinks.vue";
</script>

<template>
  <nav class="bg-white border-gray-200 px-2 sm:px-4 py-2.5 rounded dark:bg-gray-800">
    <div class="container flex flex-wrap items-center justify-between mx-auto my-2">
      <logoVue />
      <AuthButton />
      <NavigationLinksVue />
    </div>
  </nav>
</template>