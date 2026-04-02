<script setup lang="ts">
defineProps<{
  label: string
  url: string
  icon: string
}>()
</script>

<template>
  <v-btn
    :href="url"
    target="_blank"
    rel="noopener noreferrer"
    variant="outlined"
    size="large"
    block
    rounded="lg"
    class="text-none link-btn"
  >
    <v-icon start>{{ icon }}</v-icon>
    {{ label }}
  </v-btn>
</template>

<style scoped>
.link-btn {
  transition: transform 0.2s, box-shadow 0.2s;
}

.link-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.2);
}
</style>
