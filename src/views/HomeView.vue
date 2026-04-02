<script setup lang="ts">
import { useTheme } from 'vuetify'
import LinkButton from '@/components/LinkButton.vue'

const theme = useTheme()

function toggleTheme() {
  theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
}

const links = [
  {
    label: 'LinkedIn',
    url: 'https://www.linkedin.com/in/eligalayda',
    icon: 'mdi-linkedin',
  },
  {
    label: 'Email',
    url: 'mailto:eli.galayda@slalom.com',
    icon: 'mdi-email-outline',
  },
]
</script>

<template>
  <v-main>
    <v-container class="fill-height" fluid>
      <v-row align="center" justify="center">
        <v-col cols="12" sm="8" md="6" lg="4">
          <v-btn
            icon
            variant="text"
            style="position: absolute; top: 16px; right: 16px;"
            @click="toggleTheme"
          >
            <v-icon>{{ theme.global.current.value.dark ? 'mdi-weather-sunny' : 'mdi-weather-night' }}</v-icon>
          </v-btn>

          <v-card class="pa-6 text-center" variant="flat" color="transparent">
            <v-avatar size="100" class="mb-4">
              <div class="gradient-avatar" />
            </v-avatar>

            <h1 class="text-h4 font-weight-bold mb-1">Eli Galayda</h1>
            <p class="text-body-1 text-medium-emphasis mb-6">
              Consultant &middot; Builder &middot; Problem Solver
            </p>

            <div class="d-flex flex-column ga-3">
              <LinkButton
                v-for="link in links"
                :key="link.label"
                :label="link.label"
                :url="link.url"
                :icon="link.icon"
              />
            </div>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<style scoped>
.gradient-avatar {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: linear-gradient(135deg, #6366f1, #8b5cf6);
}
</style>