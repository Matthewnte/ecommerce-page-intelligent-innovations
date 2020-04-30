<template>
  <div>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="true"
      disable-resize-watcher
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      :color="setColor"
      dark
      flat
      fixed
      :app="$route.path !== '/'"
      :absolute="$route.path === '/'"
    >
      <v-app-bar-nav-icon
        class="hidden-sm-and-up"
        @click.stop="drawer = !drawer"
      />
      <v-toolbar-title>
        <nuxt-link to="/">
          <v-img
            src="https://9pay.com.ng/v2/img/9-pay-logo@3x.png"
            height="40"
            max-width="60"
            alt="Site logo"
          ></v-img>
        </nuxt-link>
      </v-toolbar-title>
      <v-spacer />
      <v-toolbar-items>
        <v-btn text nuxt href="#" class="subtitle-1 text-none mr-1">
          Need Help?
        </v-btn>
        <v-btn depressed text nuxt href="#" class="subtitle-1 text-none">
          Login
        </v-btn>
      </v-toolbar-items>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Home',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Product merchant',
          to: '/product-merchants'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Service merchant',
          to: '/service-merchants'
        }
      ],
      miniVariant: false
    }
  },
  computed: {
    setColor() {
      if (this.$route.path !== '/') {
        return 'green'
      } else {
        return 'transparent'
      }
    }
  }
}
</script>

<style scoped>
[href='#']:hover {
  border-bottom: 3px solid green;
}
</style>
