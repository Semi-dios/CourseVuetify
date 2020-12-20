<template>
  <v-app>
  
     <v-container class="pa-0 ma-0" fluid >   
         <v-row class="ma-0" height="50px">
            <v-col xs12 class="pa-0">
              <Toolbar />  
            </v-col>
          </v-row>  
        <v-container>
           <router-view/>
        </v-container>
    </v-container>
  </v-app>
</template>

<script>
import Toolbar from '@/components/partials/toolbar.vue'

export default {
  name: 'App',

  components: {
     Toolbar
  },

  data: () => ({
    //
  }),
};
</script>
