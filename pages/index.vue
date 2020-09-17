<template>
  <v-container class="white pa-0 ma-0" fluid>
    <v-row>
      <v-col cols="12" class="pa-0">
        <v-carousel
          cycle
          height="680"
          hide-delimiter-background
          show-arrows-on-hover
        >
          <v-carousel-item
            v-for="(carouseImage, i) in carouseImages"
            :key="i"
            :src="carouseImage"
          >
          </v-carousel-item>
        </v-carousel>
      </v-col>
    </v-row>
    <v-row>
      <v-col
        v-for="(product, i) in products"
        :key="i"
        cols="12"
        sm="4"
        class="pa-0"
        :style="{ backgroundColor: product.background }"
      >
        <v-card flat tile :color="product.background" class="py-5">
          <v-card-title class="justify-center">
            <strong style="color: #ffffff">{{ product.name }}</strong>
          </v-card-title>
          <v-img
            :src="product.src"
            contain
            width="40%"
            class="justify-center"
            style="margin-left: 30%"
          ></v-img>
        </v-card>
      </v-col>
    </v-row>
    <v-row style="backgroundcolor: '#E29A05'" justify="center">
      <v-col cols="12" class="pa-0">
        <v-card
          flat
          tile
          color="#E29A05"
          class="d-inline-block mx-auto"
          width="100%"
        >
          <v-container>
            <v-row justify="center">
              <v-col cols="auto">
                <v-img height="240" contain :src="juicecup"></v-img>
              </v-col>
              <v-col cols="auto" class="mx-2">
                <v-img height="240" contain :src="line"></v-img>
              </v-col>
              <v-col cols="auto" class="text-left pl-0 pt-16">
                <div class="pa-2"></div>
                <div>
                  <h2 style="color: #6b4801">ENJOY ME TIME,</h2>
                </div>
                <div class="heading">
                  <h2 style="color: #6b4801">TEA TIME,</h2>
                </div>
                <div class="heading">
                  <h2 style="color: #6b4801">ANY TIME!</h2>
                </div>
              </v-col>
            </v-row>
          </v-container>
        </v-card>
      </v-col>
    </v-row>
    <v-row class="py-8 px-14">
      <v-col
        v-for="(benefit, i) in benefits"
        :key="i"
        cols="12"
        sm="3"
        class="pa-0"
      >
        <v-card flat tile class="py-5">
          <v-img
            :src="benefit.src"
            contain
            width="30%"
            class="justify-center"
            style="margin-left: 35%"
          ></v-img>
          <v-card-title class="justify-center">
            <strong style="color: rgba(0, 0, 0, 0.7)">{{
              benefit.name
            }}</strong>
          </v-card-title>
        </v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" class="pa-0">
        <v-card flat tile class="py-5" color="#202020">
          <v-card-title class="justify-center">
            <div>
              <strong style="color: #ffffff"
                >FOLLOW US @HUMANITEA #DrinkforHumaniTea</strong
              >
            </div>
            <div>
              <strong style="color: #ffffff"> #ColdTeaDoneRight</strong>
            </div>
          </v-card-title>
        </v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" sm="4" class="pa-0">
        <v-card flat tile>
          <v-img
            :src="gridImages[0]"
            contain
            width="100%"
            aspect-ratio="1"
          ></v-img>
        </v-card>
      </v-col>
      <v-col cols="12" sm="4" class="pa-0">
        <v-card flat tile>
          <v-img
            :src="gridImages[5]"
            contain
            width="100%"
            aspect-ratio="1"
            class="align-center"
          >
            <v-row justify="center">
              <v-icon x-large dark>mdi-play</v-icon>
            </v-row>
          </v-img>
        </v-card>
      </v-col>
      <v-col cols="12" sm="4" class="pa-0">
        <v-card flat tile>
          <v-img
            :src="gridImages[1]"
            contain
            width="100%"
            aspect-ratio="1"
          ></v-img>
        </v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" sm="4" class="pa-0">
        <v-card flat tile>
          <v-img
            :src="gridImages[2]"
            contain
            width="100%"
            aspect-ratio="1"
          ></v-img>
        </v-card>
      </v-col>
      <v-col cols="12" sm="4" class="pa-0">
        <v-card flat tile>
          <v-img
            :src="gridImages[3]"
            contain
            width="100%"
            aspect-ratio="1"
          ></v-img>
        </v-card>
      </v-col>
      <v-col cols="12" sm="4" class="pa-0">
        <v-card flat tile>
          <v-img
            :src="gridImages[4]"
            contain
            width="100%"
            aspect-ratio="1"
          ></v-img>
        </v-card>
      </v-col>
    </v-row>
    <v-card flat tile color="#202020" class="px-16 pt-4 pb-8">
      <v-snackbar v-model="snackbar" absolute top right color="success">
        <span>Registration successful!</span>
        <v-icon dark>mdi-checkbox-marked-circle</v-icon>
      </v-snackbar>
      <v-form ref="form" @submit.prevent="submit">
        <v-container fluid>
          <v-row>
            <v-col>
              <v-card-title class="justify-center">
                <h2 style="color: #ffffff">CONTACT US</h2>
              </v-card-title>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="12" sm="6">
              <v-text-field
                v-model="form.name"
                :rules="rules.name"
                background-color="white"
                color="#202020"
                label="Name"
                required
                filled
              ></v-text-field>
            </v-col>
            <v-col cols="12" sm="6">
              <v-text-field
                v-model="form.email"
                :rules="rules.name"
                background-color="white"
                color="#202020"
                label="Email"
                required
                filled
              ></v-text-field>
            </v-col>
            <v-col cols="12">
              <v-textarea
                v-model="form.message"
                background-color="white"
                color="#202020"
                label="Message (optional)"
                filled
              >
              </v-textarea>
            </v-col>
          </v-row>
        </v-container>
        <v-card-actions>
          <v-btn
            :disabled="!formIsValid"
            rounded
            color="#E29A05"
            type="submit"
            dark
            >Send</v-btn
          >
        </v-card-actions>
      </v-form>
    </v-card>
  </v-container>
</template>

<script>
export default {
  data() {
    const defaultForm = Object.freeze({
      name: '',
      email: '',
      message: '',
    })
    return {
      form: Object.assign({}, defaultForm),
      rules: {
        name: [
          (val) => (val || '').length > 0 || 'This field is required',
          (val) =>
            (val && val.length <= 60) || 'Name must be less than 10 characters',
        ],
        email: [
          (v) => !!v || 'E-mail is required',
          (v) => /.+@.+\..+/.test(v) || 'E-mail must be valid',
        ],
      },
      snackbar: false,
      terms: false,
      defaultForm,
      valid: true,
      carouseImages: [
        require('~/assets/images/Tina Hero Image_Small.JPG'),
        require('~/assets/images/Tina Hero Image 2_Small.jpg'),
        require('~/assets/images/Tina Hero Image 3_Small.jpg'),
      ],
      gridImages: [
        require('~/assets/images/Grid_1.png'),
        require('~/assets/images/Grid_2.png'),
        require('~/assets/images/Grid_3.png'),
        require('~/assets/images/Grid_4.png'),
        require('~/assets/images/Grid_5.png'),
        require('~/assets/images/Grid_6.png'),
      ],
      benefits: [
        {
          name: 'ORGANIC',
          src: require('~/assets/images/Benefits_1.png'),
        },
        {
          name: 'ECO-FRIENDLY',
          src: require('~/assets/images/Benefits_2.png'),
        },
        {
          name: 'VEGAN',
          src: require('~/assets/images/Benefits_3.png'),
        },
        {
          name: 'LOW SUGAR & CALORIES',
          src: require('~/assets/images/Benefits_4.png'),
        },
      ],
      benefitsImage: require('~/assets/images/Benefits_1.png'),
      products: [
        {
          name: 'EARL GREY',
          src: require('~/assets/images/Product_1.png'),
          background: '#7D72B3',
        },
        {
          name: 'ROOIBOS',
          src: require('~/assets/images/Product_2.png'),
          background: '#D33846',
        },
        {
          name: 'MATCHA',
          src: require('~/assets/images/Product_3.png'),
          background: '#66BF72',
        },
      ],
      juicecup: require('~/assets/images/Juicecup.png'),
      line: require('~/assets/images/Line.png'),
    }
  },
  computed: {
    formIsValid() {
      return this.form.name && this.form.email
    },
  },
  methods: {
    resetForm() {
      this.form = Object.assign({}, this.defaultForm)
      this.$refs.form.reset()
    },
    submit() {
      this.snackbar = true
      this.resetForm()
    },
  },
}
</script>
First
