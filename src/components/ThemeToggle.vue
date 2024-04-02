<template>
  <div class="theme-toggle">
    <v-switch @click="toggleTheme" label="🌗"></v-switch>
  </div>
</template>

<script setup>
import { useTheme } from 'vuetify'

const theme = useTheme()

function toggleTheme () {
  theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
}
</script>

<style scoped>

.theme-toggle {
  position: fixed;
  top: 1rem;
  right: 2rem;
}

</style>
