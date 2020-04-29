<template>
  <v-carousel
    height="450"
    hide-delimiters
    hide-delimiter-background
    show-arrows-on-hover
  >
    <v-carousel-item v-for="(image, i) in images" :key="i" :src="image.src">
      <v-container fluid class="fill-height cover-sm">
        <v-container>
          <v-btn color="green" x-large depressed>
            Shop Now<v-icon large right>mdi-chevron-right</v-icon>
          </v-btn>
        </v-container>
      </v-container>
    </v-carousel-item>
  </v-carousel>
</template>

<script>
export default {
  data: () => ({
    images: [
      {
        src: '/carousel2.jpg'
      },
      {
        src: '/carousel1.jpeg'
      },
      {
        src: '/carousel3.jpg'
      }
    ]
  })
}
</script>

<style scoped>
.cover-sm {
  background: rgba(0, 50, 0, 0.2);
  height: 70vh;
}
</style>
