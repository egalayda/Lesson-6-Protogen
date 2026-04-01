<script setup lang="ts">
defineProps<{
  isDark: boolean
}>()

const emit = defineEmits<{
  (e: 'toggleDark'): void
}>()

const links = [
  {
    label: 'LinkedIn',
    href: 'https://www.linkedin.com/in/eligalayda',
    icon: '??',
  },
  {
    label: 'Email',
    href: 'mailto:eli.galayda@slalom.com',
    icon: '??',
  },
]
</script>

<template>
  <main class="page">
    <button class="toggle-btn" @click="emit('toggleDark')" :aria-label="isDark ? 'Switch to light mode' : 'Switch to dark mode'">
      {{ isDark ? '??' : '??' }}
    </button>

    <div class="card">
      <div class="avatar" aria-label="Profile photo placeholder"></div>

      <h1 class="name">Eli Galayda</h1>
      <p class="tagline">Consultant · Builder · Problem Solver</p>

      <nav class="links">
        <a
          v-for="link in links"
          :key="link.label"
          :href="link.href"
          class="link-btn"
          target="_blank"
          rel="noopener noreferrer"
        >
          <span class="link-icon">{{ link.icon }}</span>
          {{ link.label }}
        </a>
      </nav>
    </div>
  </main>
</template>

<style scoped>
.page {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 2rem 1rem;
  position: relative;
}

.toggle-btn {
  position: absolute;
  top: 1.25rem;
  right: 1.25rem;
  background: transparent;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
  padding: 0.25rem;
  line-height: 1;
  border-radius: 50%;
  transition: transform 0.2s;
}

.toggle-btn:hover {
  transform: scale(1.2);
}

.card {
  width: 100%;
  max-width: 480px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

.avatar {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background: linear-gradient(135deg, #6366f1, #8b5cf6);
  flex-shrink: 0;
}

.name {
  font-size: 1.75rem;
  font-weight: 700;
  letter-spacing: -0.5px;
  text-align: center;
}

.tagline {
  font-size: 0.95rem;
  opacity: 0.6;
  text-align: center;
  font-weight: 400;
}

.links {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  width: 100%;
  margin-top: 0.5rem;
}

.link-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.6rem;
  width: 100%;
  padding: 0.85rem 1.5rem;
  border-radius: 0.75rem;
  font-family: 'Inter', sans-serif;
  font-size: 1rem;
  font-weight: 500;
  text-decoration: none;
  border: 1.5px solid currentColor;
  color: inherit;
  transition: background-color 0.2s, transform 0.2s, box-shadow 0.2s;
}

.link-btn:hover {
  background-color: rgba(128, 128, 128, 0.15);
  transform: translateY(-2px);
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.2);
}

.link-icon {
  font-size: 1.1rem;
}
</style>
