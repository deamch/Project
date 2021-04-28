<template>
  <v-app>
    <Navbar/>
    
    <v-content>
    <Mainpage/> 
    </v-content>

    <v-footer  dark  padless>
      <v-card  class="flex" flat  tile>
        <v-card-title class="teal">
          <strong class="subheading">Get connected with us on social networks!</strong>
          <v-spacer></v-spacer>

          <v-btn  v-for="icon in icons" :key="icon"  class="mx-4" dark  icon >
            <v-icon size="24px">
              {{ icon }}
            </v-icon>
          </v-btn>
        </v-card-title>

        <v-card-text class="py-2 white--text text-center">
          {{ new Date().getFullYear() }} — <strong>Our Project</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
import Navbar from '@/components/Navbar'
import Mainpage from '@/components/Mainpage'


export default {
  name: 'App',

  components: {
    Navbar,
    Mainpage,
  },

  data () {
    return {
      icons: [
        'mdi-facebook',
        'mdi-twitter',
        'mdi-telegram',
        'mdi-instagram',
      ],
    }
  }
};
</script>
