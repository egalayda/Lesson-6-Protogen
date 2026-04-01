<script setup lang="ts">
import { ref } from 'vue'
import { RouterView } from 'vue-router'

const isDark = ref(true)
</script>

<template>
  <div :class="isDark ? 'dark' : 'light'" class="app-root">
    <RouterView :is-dark="isDark" @toggle-dark="isDark = !isDark" />
  </div>
</template>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Inter', sans-serif;
}

.app-root {
  min-height: 100vh;
  transition: background-color 0.3s, color 0.3s;
}

.app-root.dark {
  background-color: #0f0f0f;
  color: #f0f0f0;
}

.app-root.light {
  background-color: #f5f5f5;
  color: #111111;
}
</style>
