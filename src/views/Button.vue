<template>
  <v-container>
   <v-layout wrap>
      <v-flex>
        <v-btn
        elevation="2"
          >Button</v-btn>
      
    </v-flex>
    <v-flex>
        <v-btn
        color="primary"
          >Button</v-btn>
    </v-flex>
    <v-flex>
        <v-btn
         color="blue" dark
          >Button</v-btn>
    </v-flex>
    <v-flex>
        <v-btn
         color="blue" text
          >Button</v-btn>
    </v-flex>
    <v-flex>
        <v-btn
         color="blue" large
          >Button</v-btn>
    </v-flex>
    <v-flex>
        <v-btn
         color="secondary" small
          >Button</v-btn>
    </v-flex>
    <v-flex>
        <v-btn
         color="info" depressed
          >Button</v-btn>
    </v-flex>
    <v-flex>
        <v-btn icon 
         color="info" 
          > <v-icon> mdi-minus</v-icon>
        </v-btn>
    </v-flex>
    <v-flex>
        <v-btn
        class="mx-2"
        fab
        dark
        large
        color="purple"
      >
        <v-icon dark>
          mdi-android
        </v-icon>
      </v-btn>
    </v-flex>
    <v-flex>
        <v-btn
        class="mx-2"
        fab
        dark
        small
        color="primary"
      >
        <v-icon dark>
          mdi-android
        </v-icon>
      </v-btn>
    </v-flex>
   </v-layout>
  </v-container>
</template>

<script>
export default {
  name:'Button',
  data() {
    return{

    }
  }
}
</script>