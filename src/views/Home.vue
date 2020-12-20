<template>
  <div>
    <v-row>
      <v-col sm="12" md="6">
        <v-card>
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
            height="200px"
          ></v-img>

          <v-card-title> Top western road trips </v-card-title>

          <v-card-subtitle> 1,000 miles of wonder </v-card-subtitle>
          <v-card-actions>
            <v-btn color="info" dark @click="dialog = !dialog">Action</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
      <v-col sm="12" md="6">
        <v-card>
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
            height="200px"
          >
          <v-container>
            <v-row>
              <v-col> 
                <span >
                  Texto
                  </span></v-col> </v-row
          >
          </v-container>
          </v-img>

          <v-card-title> Top western road trips </v-card-title>

          <v-card-subtitle> 1,000 miles of wonder </v-card-subtitle>
          <v-card-actions>
            <v-btn color="info" dark @click="dialog = !dialog">Action</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
    <v-dialog
     v-model="dialog"
      width="500">
        <v-card>
          <v-card-title>
            This is a modal
          </v-card-title>
          <v-divider>

          </v-divider>
          <v-card-actions>
             <v-btn color="info" dark @click="dialog = false">Back</v-btn>
          </v-card-actions>
        </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
  data(){
    return {
      dialog: false
          }

  }
};
</script>
