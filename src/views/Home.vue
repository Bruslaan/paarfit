<template>
  <div class="home">
    <!-- <p>{{$store.getters.name}}</p>
  <p>User: {{$store.getters["user/name"]}}</p>
    <p>Token: {{$store.getters["user/token"]}}</p>-->
    <!-- <p> {{$store.getters["user/avatar"]}}</p> -->
    <!-- <p>Setting: {{$store.getters.fixedHeader}}</p> -->

    <v-layout>
      <v-row justify="center" align="center">
        <div>
          <h1 class="text-center ma-3">Woche 1</h1>
          <v-btn class="ma-3">Start Workout</v-btn>
          <v-timeline>
            <v-timeline-item right>timeline item</v-timeline-item>
            <v-timeline-item right>timeline item</v-timeline-item>
            <v-timeline-item right>timeline item</v-timeline-item>
          </v-timeline>
        </div>
      </v-row>
    </v-layout>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "home",
  components: {}
};
</script>
