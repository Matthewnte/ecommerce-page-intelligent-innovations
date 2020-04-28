<template>
  <v-carousel cycle height="500" hide-delimiter show-arrows-on-hover>
    <v-carousel-item
      v-for="(image, i) in images"
      :key="i"
      :src="image.src"
    ></v-carousel-item>
  </v-carousel>
</template>

<script>
export default {
  data: () => ({
    images: [
      {
        src: '/carousel3.jpg'
      },
      {
        src: '/carousel2.jpg'
      },
      {
        src: '/carousel1.jpg'
      }
    ]
  })
}
</script>
