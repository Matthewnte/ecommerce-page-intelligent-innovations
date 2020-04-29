<template>
  <v-row>
    <v-col
      v-for="(merchant, index) in merchants"
      :key="index"
      cols="6"
      sm="4"
      md="3"
    >
      <v-card flat>
        <v-img :src="merchant.src" height="200px"></v-img>
        <v-card-title class="body-1">{{ merchant.title }}</v-card-title>
        <v-card-subtitle>{{ merchant.subtitle }}</v-card-subtitle>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  props: {
    merchants: Array
  }
}
</script>
