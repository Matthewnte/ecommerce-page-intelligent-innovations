<template>
  <v-container>
    <div class="text-center pt-12 pb-6">
      <h2 id="title" class="title font-weight-bold">Merchants</h2>
      <p class="text--secondary">
        See a list of our products by product categorization
      </p>
    </div>
    <v-row>
      <v-col cols="12" class="mb-6" offset-sm-3>
        <v-btn
          v-for="(category, i) in categories"
          id="category-btn"
          :key="i"
          color="success"
          outlined
          nuxt
          :to="category.route"
          text
          class="title text-none py-7 mr-3"
        >
          {{ category.title }}
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'MerchantCategory',
  data: () => ({
    categories: [
      { title: 'Home', route: '/' },
      { title: 'Service merchants', route: '/service-merchants' },
      { title: 'Product merchants', route: '/product-merchants' }
    ]
  })
}
</script>

<style scoped>
#title {
  font-size: 24px !important;
}
a#category-btn {
  border: 1.5px #00e676 solid !important;
}
a.v-btn--active {
  color: white !important;
  background: #00e676;
}
</style>
