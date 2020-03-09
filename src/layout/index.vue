<template>
  <v-app>
    <!-- <Drawer v-model="drawer"/> -->
    <v-app-bar fixed app  color="white" elevate-on-scroll>
      <ul class="d-flex justify-center">
        <li>
          <router-link :to="{name: 'home'}">Home</router-link>
        </li>
        <li>
          <router-link :to="{name: 'profile'}">Profile</router-link>
        </li>
        <li>
          <router-link :to="{name: 'profile'}">Ernährung</router-link>
        </li>
      </ul>
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

<style lang="css" scoped>
ul {
  list-style-type: none;
  justify-content: center;
  width: 100%;
  margin: 0;
  padding: 0;
  overflow: hidden;
  /* background-color: grey; */
}

li {
  float: left;
  /* border-right: 1px solid grey; */
}

li a {
  display: block;
  color: grey;
  text-align: center;
  justify-content: center;
  padding: 5px 16px;
  text-decoration: none;
}
li:last-child {
  border-right: none;
}

.active {
  /* background-color: grey; */
  color: black;
  /* border: solid 1px; */
   border-bottom: solid 2px grey;
}
</style>