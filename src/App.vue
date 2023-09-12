<script setup>
import { RouterLink, RouterView } from 'vue-router'
import DefaultLayout from './layouts/DefaultLayout.vue'
import HomeViewVue from './views/HomeView.vue'
// import { ref, onMounted } from 'vue'
// import { loginStore } from '@/stores/index'
</script>

<template>
  <v-app id="app">
    <DefaultLayout></DefaultLayout>
    <v-main>
      <router-view></router-view>
      
    </v-main>
</v-app>

  <RouterView />
</template>

<style scoped>
</style>
