<template>
  <v-app>
    <v-system-bar
      color="#202020"
      dark
      height="40"
      app
      class="text-center px-16"
    >
      <v-spacer></v-spacer>
      <v-btn icon class="ml-4">
        <v-icon>mdi-twitter</v-icon>
      </v-btn>
      <v-btn icon class="ml-4">
        <v-icon>mdi-facebook</v-icon>
      </v-btn>
      <v-btn icon class="ml-4 mr-10">
        <v-icon>mdi-instagram</v-icon>
      </v-btn>
      <v-btn icon class="mx-16">
        <v-icon class="mr-4">mdi-shopping-outline</v-icon> 0 ITEMS
      </v-btn>
    </v-system-bar>
    <v-app-bar
      app
      color="rgba(0, 0, 0, 1)"
      flat
      hide-on-scroll
      class="text-center"
      scroll-threshold="250"
    >
      <v-img
        class="mx-2"
        :src="logo"
        max-height="150"
        max-width="150"
        style="cursor: pointer"
        @click="navigateHome"
      ></v-img>
      <v-spacer></v-spacer>
      <v-btn nuxt to="/shop" text color="white">SHOP</v-btn>
      <v-btn nuxt to="/blog" text color="white">BLOG</v-btn>
      <v-btn nuxt to="/about" text color="white">ABOUT US</v-btn>
      <v-btn nuxt to="/contact" text color="white">CONTACT</v-btn>
      <v-btn nuxt to="/subscribe" class="mx-2" outlined color="#E29A05" rounded
        >SUBSCRIBE</v-btn
      >
    </v-app-bar>
    <v-main>
      <nuxt />
    </v-main>
    <v-footer padless>
      <v-container class="white pa-0 ma-0" fluid>
        <v-row class="white px-16">
          <v-col cols="12" md="6">
            <v-card flat tile>
              <v-card-title>
                <strong style="color: #797979">LOCATION</strong>
              </v-card-title>
              <v-card-text style="color: #797979">
                Mighty Drinks Ltd.
              </v-card-text>
              <v-card-text style="color: #797979">
                Kemp House, 160 City Road, London, United Kingdom, EC1V 2NX
              </v-card-text>
              <v-card-text style="color: #797979">
                Company Number: 11714034
              </v-card-text>
            </v-card>
          </v-col>
          <v-col cols="12" md="3">
            <v-card flat tile>
              <v-card-title>
                <strong style="color: #797979">INFORMATION</strong>
              </v-card-title>
              <v-card-actions>
                <v-btn text color="#797979">Delivery and returns</v-btn>
              </v-card-actions>
              <v-card-actions>
                <v-btn text color="#797979">Terms of service</v-btn>
              </v-card-actions>
              <v-card-actions>
                <v-btn text color="#797979">Privacy policy</v-btn>
              </v-card-actions>
              <v-card-actions>
                <v-btn text color="#797979">Cookie policy</v-btn>
              </v-card-actions>
              <v-card-actions>
                <v-btn text color="#797979">Join the team</v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
          <v-col cols="12" md="3">
            <v-card flat title>
              <v-card-title>
                <strong style="color: #797979">FOLLOW US</strong>
              </v-card-title>
              <v-card-actions>
                <v-btn text color="#797979">Instagram</v-btn>
              </v-card-actions>
              <v-card-actions>
                <v-btn text color="#797979">Facebook</v-btn>
              </v-card-actions>
              <v-card-actions>
                <v-btn text color="#797979">Twitter</v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
        <v-row no-gutters>
          <v-col col="12">
            <v-card flat tile class="black white--text text-center">
              <v-card-text class="white--text">
                <strong>All rights reserved © Mighty Drinks Ltd. 2020</strong>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
      logo: require('~/assets/images/humanitea-logo.png'),
    }
  },
  methods: {
    navigateHome() {
      this.$router.push('/')
    },
  },
}
</script>
