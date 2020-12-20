<template>
 <div>
   <v-toolbar app
  color="blue"
  dense
  
  
  
>
<v-app-bar-nav-icon  @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
<v-toolbar-title>Vutify</v-toolbar-title>
<v-spacer></v-spacer>
  <v-btn class="success" >
  Loggin</v-btn>
  <v-btn class="error ml-3">
 Logout</v-btn>
  </v-toolbar>
   <v-navigation-drawer
      v-model="drawer"
      dark
      app
      temporary
      absolute
      class="pa-3"
    >
     <v-list-item-avatar>
          <v-img src="https://randomuser.me/api/portraits/men/78.jpg"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>{{user}}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
      <v-divider></v-divider>

      <v-list dense>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content >
            <v-list-item-title class="d-flex align-center" ><v-btn text :to='{name: item.url}'>{{ item.title }}</v-btn></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
 </div>

  
</template>

<script>
export default {
  name: 'toolbar',
  data() {
    return {
      drawer: false,
      items: [
          { title: 'Home', icon: 'mdi-view-dashboard',url: 'Home' },
          { title: 'Task', icon: 'mdi-desktop-classic' , url: 'Task'},
        ],
        user: 'Sergio Andres Penagos'
    }
  }
}
</script>

<style scoped>


</style>