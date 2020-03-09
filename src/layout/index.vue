<template>
  <v-app>
    <!-- <Drawer v-model="drawer"/> -->
    <v-app-bar app absolute color="white" elevate-on-scroll>
      <v-toolbar-title @click="$router.push({name:'home'})">PaarFit</v-toolbar-title>
      <v-spacer></v-spacer>
      <!-- <router-link :to="{name: 'home'}">Home</router-link> -->
     
      <!-- <v-btn icon @click="drawer=!drawer"><v-icon>mdi-menu</v-icon></v-btn> -->

      <v-menu offset-y>
        <template v-slot:activator="{ on }">
          <v-btn icon v-on="on">
            <v-icon>mdi-menu</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item @click="logout">
            <v-list-item-icon>
              <v-icon>mdi-run</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Logout</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
    <!-- Sizes your content based upon application components -->
    <v-content>
      <!-- Provides the application the proper gutter -->
      <v-container fluid>
        <!-- If using vue-router -->
        <router-view :key="key" />
      </v-container>
    </v-content>

    <v-footer app>
      <!-- -->
    </v-footer>
  </v-app>
</template>

<script>
// import Drawer from "./drawer";
export default {
  data() {
    return {
      drawer: false
    };
  },
  // components: { Drawer },
  computed: {
    key() {
      return this.$route.path;
    }
  },
  methods: {
    async logout() {
      await this.$store.dispatch("user/logout");
      this.$router.push(`/login?redirect=${this.$route.fullPath}`);
    }
  }
};
</script>

<style>
</style>