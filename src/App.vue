<template>
  <div class="flex flex-col min-h-screen font-Roboto bg-weather-primary">
    <Nagivation />
    <RouterView class="flex-1" v-slot="{ Component }">
      <Transition name="page">
        <component :is="Component" />
      </Transition>
    </RouterView>
  </div>
</template>

<script setup lang="ts">
import {  RouterView } from 'vue-router'
import Nagivation from './components/Nagivation.vue';
</script>