<template>
  <div>
    <Carousel v-if="$route.path === '/'" />
    <Categories />
    <Merchants :merchants="merchants" />
  </div>
</template>
<script>
import data from '../data'
import Carousel from '@/components/Carousel'
import Categories from '@/components/Category'
import Merchants from '@/components/Merchants'

export default {
  components: {
    Carousel,
    Categories,
    Merchants
  },
  data: () => ({
    merchants: data.merchants
  })
}
</script>
