<template>
  <v-app>
    <AppBar />
    <v-content>
      <v-container fluid class="pa-0">
        <nuxt />
      </v-container>
    </v-content>
    <v-footer>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
import AppBar from '@/components/AppBar'

export default {
  components: {
    AppBar
  }
}
</script>

<style>
p {
  font-size: 18px;
}
</style>
