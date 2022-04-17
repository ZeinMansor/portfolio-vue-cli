<template>
  <v-app id="inspire">
    

    <v-navigation-drawer
      v-model="drawer"
      app
      width="300"
      class="ma-0"
    >
      <v-sheet
        color="grey lighten-4"
        class="pa-4"
      >
        <v-avatar
          class="mb-4"
          color="grey darken-1"
          size="64"
        ></v-avatar>

        <div>john@vuetifyjs.com</div>
      </v-sheet>

      <v-divider></v-divider>

      <v-list>
        <v-list-item
          v-for="i in icons"
          :key="i.id"
          link 
          class="my-4"
          :href="i.link"
          @click="$vuetify.goTo(i.link , options)"
        >
          <router-link style="text-decoration: none; color: inherit;" :to="i.link">

          <v-row>
          
          <v-list-item-icon >
            <v-icon
              :size="i.size"
              :href="i.link"
              color="blue lighten-2"
            >{{ i.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ i.name }}</v-list-item-title>
          </v-list-item-content>
          
          </v-row>
          </router-link>
        
        </v-list-item>
      
      </v-list>
    </v-navigation-drawer>
      
    <v-main>

      <LandingComponent />
      <AboutComponent />

    </v-main>
  </v-app>
</template>






<script>
import LandingComponent from "../components/Landing/LandingComponent.vue";
import AboutComponent from "../components/About/AboutComponent.vue"
  export default {
    name: "MainPage",
    components: {
      LandingComponent,
      AboutComponent
    },
    data: function() {
      return {
        cards: ['Today', 'Yesterday'],
        drawer: null,  
          icons: [
            {
              id: '1',
              name: 'Home',
              icon: 'mdi-home',
              link: '#home',
              size: '30'
            },

            {
              id: '2',
              name: 'About',
              icon: 'mdi-music-clef-treble',
              link: '#About',
              size: '30'
            },

            {
              id: '6',
              name: 'Education',
              icon: 'mdi-library',
              link: '/',
              size: '30'
            },

            {
              id: '3',
              name: 'Resume',
              icon: 'mdi-account-box',
              link: '/',
              size: '30'
            },

            {
              id: '4',
              name: 'Projects',
              icon: 'mdi-home',
              link: '/',
              size: '30'
            },

            {
              id: '5',
              name: 'Contact',
              icon: 'mdi-card-account-phone',
              link: '/',
              size: '30'
            }

          ]
        }
    }, 
    computed : {
      options () {
        return {
          duration: 1000,
          offset: -20,
          easing: 'easeInOutCubic',
        }
      }
    }
  }
</script>

<style>

</style>