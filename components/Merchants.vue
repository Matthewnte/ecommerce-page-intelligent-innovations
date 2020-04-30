<template>
  <v-container>
    <v-row>
      <v-col>
        <v-text-field
          v-model="filter"
          outlined
          hide-details
          clearable
          flat
          label="Filter Merchants..."
        ></v-text-field>
      </v-col>
      <v-col class="d-flex justify-end align-end">
        <v-menu offset-y>
          <template v-slot:activator="{ on }">
            <v-btn outlined large class="text-none" v-on="on">
              Sort by<v-icon right>mdi-chevron-down</v-icon>
            </v-btn>
          </template>
          <v-list>
            <v-list-item
              v-for="(item, index) in items"
              :key="index"
              @click="sortBy('title')"
            >
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-col>
    </v-row>
    <!-- List of merchants -->
    <v-row>
      <v-col
        v-for="(merchant, index) in merchants"
        :key="index"
        cols="6"
        sm="4"
        md="3"
      >
        <v-card flat hover min-height="300">
          <v-img :src="merchant.src" height="200px">
            <v-container
              class="fill-height"
              style="background: rgba(0, 50, 0, 0.1);"
            ></v-container>
          </v-img>
          <v-card-text class="title text--secondary d-flex justify-center">
            {{ merchant.title }}
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  props: {
    merchants: {
      type: Array,
      required: true
    }
  },
  data: () => ({
    items: [{ title: 'Merchant name' }],
    filter: ''
  }),
  computed: {
    filteredMerchants() {
      return this.merchants.filter((merchant) => {
        merchant.title.toLowerCase().includes(this.filter.toLowerCase())
      })
    }
  },
  methods: {
    sortBy(prop) {
      this.merchants.sort((first, second) => {
        if (first[prop] < second[prop]) return -1
        return 1
      })
    }
  }
}
</script>
