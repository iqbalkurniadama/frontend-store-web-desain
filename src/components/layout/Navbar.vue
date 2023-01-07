<script setup>
import { onMounted, computed } from "vue";
import { useUserStore } from "../../stores/user";

import LogoVue from "./Logo.vue";
import AuthButton from "./AuthButton.vue";
import NavigationLinksVue from "./NavigationLinks.vue";
import UserInfoVue from "./UserInfo.vue";

const userStore = useUserStore()
const isLoggedIn = computed(() => userStore.isLoggedIn)
const user = computed(() => userStore.user)

onMounted(() => {
  userStore.fetchUser()
})

</script>

<template>
  <nav class="bg-white border-gray-200 px-2 sm:px-4 py-2.5 rounded dark:bg-gray-800">
    <div class="container flex flex-wrap items-center justify-between mx-auto my-2">
      <LogoVue />
      <UserInfoVue v-if="isLoggedIn" :user="user.data" />
      <AuthButton v-else />
      <NavigationLinksVue />
    </div>
  </nav>
</template>