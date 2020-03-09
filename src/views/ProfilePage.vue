<template>
  <div>
    <v-card outlined class="justify-center">
      <v-card-title class="d-flex justify-center py-6">
        <v-col justify="center" align="center">
          <v-avatar class="ma-4" size="90">
            <v-img :src="$store.getters['user/avatar']" alt="John">
              <template v-slot:placeholder>
                <v-row class="fill-height ma-0" align="center" justify="center">
                  <v-progress-circular indeterminate color="grey lighten-2"></v-progress-circular>
                </v-row>
              </template>
            </v-img>
          </v-avatar>
          <!-- <a @click="$router.push('/profilePage')" class="ml-2">{{item.name}}</a> -->

          <h1 class="font-weight-bold display-1">Dei Mudda</h1>

          <p class="text--secondary">Hier steht irgendwas über sein Wesen</p>
        </v-col>
      </v-card-title>

      <div class="d-flex justify-space-between mx-4">
        <v-col class="pa-0">
          <p class="mb-0 pa-0">0</p>
          <p class="mb-0 pa-0">Workouts</p>
        </v-col>
        <v-col class="pa-0">
          <p class="mb-0 pa-0">0</p>
          <p class="mb-0 pa-0">Wochen</p>
        </v-col>
        <v-col class="pa-0">
          <p class="mb-0 pa-0">0</p>
          <p class="mb-0 pa-0">Freunde</p>
        </v-col>
        <v-col class="pa-0">
          <p class="mb-0 pa-0">0</p>
          <p class="mb-0 pa-0">Workouts</p>
        </v-col>
      </div>
      <v-layout class="d-flex justify-center mt-4 mx-4">
        <v-row justiry="center" align="center">
          <v-col>
            <v-progress-linear color="light-green darken-4" height="10" value="20" striped></v-progress-linear>
          </v-col>
        </v-row>
      </v-layout>
      <div class="d-flex justify-space-between mb-5 mx-4">
        <p class="ma-0">Anfänger</p>
        <p class="ma-0">Meister</p>
      </div>

      <!-- <v-tabs v-model="tab" centered grow background-color="light-grey">
        <v-tab v-for="item in items" :key="item">{{ item }}</v-tab>
      </v-tabs>-->
      <ul class="d-flex justify-center">
        <li>
          <a :class="tab == 0 ? {'active':true}:{'active':false} " @click="tab=0">Home</a>
        </li>
        <li>
          <a :class="tab == 1 ? {'active':true}:{'active':false} " @click="tab=1">News</a>
        </li>
        <li>
          <a :class="tab == 2 ? {'active':true}:{'active':false} " @click="tab=2">Contact</a>
        </li>
        <li>
          <a :class="tab == 3 ? {'active':true}:{'active':false} " @click="tab=3">About</a>
        </li>
      </ul>

      <v-tabs-items v-model="tab">
        <v-tab-item>
          <v-card color="basil" flat>
            <v-layout wrap class="pa-3 mt-5">
              <v-row class="justify-center">
                <Informationen :data="PersonalInformation" text="Personal Information" />
              </v-row>
            </v-layout>
          </v-card>
        </v-tab-item>
        <v-tab-item>
          <v-card color="basil" flat>
            <v-layout wrap class="pa-3 mt-5">nix hier</v-layout>
          </v-card>
        </v-tab-item>
      </v-tabs-items>
    </v-card>
  </div>
</template>

  
<script>
import Informationen from "../components/Formular";
export default {
  components: { Informationen },
  computed: {
    activeIndex() {
      return { active: true };
    }
  },
  data() {
    return {
      tab: 0,
      items: ["Information", "Anwesenheit", "Abwesenheit", "Rollen"],
      PersonalInformation: {
        Vorname: "Josef",
        Nachname: "Meier",
        Wohnort: "Maraschki Straße 12",
        SteuerID: 12
      },
      AndereInformationen: {
        Bank: "Mascha Kascha",
        "Name des Kontoinhabers": "Meier",
        IBAN: "as123asdRoll",
        BIC: "22222"
      }
    };
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
}

li a {
  display: block;
  color: grey;
  text-align: center;
  justify-content: center;
  padding: 5px 16px;
  text-decoration: none;
}

.active {
  /* background-color: grey; */
  color: black;
  /* border: solid 1px; */
  border-bottom: solid 2px grey;
}
</style>