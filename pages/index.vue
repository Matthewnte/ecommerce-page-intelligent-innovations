<template>
  <div>
    <Carousel />
    <v-container>
      <h2 class="headline font-weight-bold">Merchants</h2>
      <Merchants :merchants="merchants" />
    </v-container>
  </div>
</template>

<script>
import data from '../data'
import Carousel from '@/components/Carousel'
import Merchants from '@/components/Merchants'

export default {
  components: {
    Carousel,
    Merchants
  },
  data: () => ({
    merchants: data.merchants
  })
}
</script>
