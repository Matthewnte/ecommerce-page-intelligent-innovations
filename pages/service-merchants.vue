<template>
  <div>
    <Categories />
    <Merchants :merchants="filterServices" />
  </div>
</template>

<script>
import data from '../data'
import Categories from '@/components/Category'
import Merchants from '@/components/Merchants'

export default {
  components: {
    Categories,
    Merchants
  },
  computed: {
    filterServices() {
      return data.merchants.filter((merchant) => {
        return merchant.category === 'service'
      })
    }
  }
}
</script>
