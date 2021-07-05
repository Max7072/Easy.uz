<template>
  <div>
     <v-app-bar
      app
      color="dark"
      dark
      hide-on-scroll
    >
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Easy.uz</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
    </v-app-bar>
    <!-- drawer -->
    <v-navigation-drawer
      v-model="drawer"
      app
      dark
      width="20%"
      temporary
    >
    <v-list-item >
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            Easy.uz
          </v-list-item-title>
          <v-list-item-subtitle>
            Biz bilan biznes boshlang
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
      <v-divider></v-divider>
      <v-list>
        <v-list-item
          v-for=" item in items"
          :key="item.index"
          link
          :to="item.to"
          class="blue--text"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ item.text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
     data() {
         return {
           drawer: false,
           items:[
             {text: 'Home', icon:'mdi-home', to: '/'},
             {text:'Reja', icon: 'mdi-file-edit', to: 'questions'},
             {text: 'Qo\'llanma', icon:'mdi-file', to: 'documentation'},
           ]
         }
     },

}
</script>

<style>

</style>