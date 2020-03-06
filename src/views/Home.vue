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
          <v-btn
            class="ma-3 pulse-button"
            text
            @click="$router.push({name:'workout'})"
          >Start Workout</v-btn>
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

<style lang="css">
.pulse-button {
  position: relative;

  border: none;
  box-shadow: 0 0 0 0 rgba(232, 76, 61, 0.7);

  cursor: pointer;
  -webkit-animation: pulse 1.25s infinite cubic-bezier(0.66, 0, 0, 1);
  -moz-animation: pulse 1.25s infinite cubic-bezier(0.66, 0, 0, 1);
  -ms-animation: pulse 1.25s infinite cubic-bezier(0.66, 0, 0, 1);
  animation: pulse 1.25s infinite cubic-bezier(0.66, 0, 0, 1);
}
.pulse-button:hover {
  -webkit-animation: none;
  -moz-animation: none;
  -ms-animation: none;
  animation: none;
}

@-webkit-keyframes pulse {
  to {
    box-shadow: 0 0 0 45px rgba(232, 76, 61, 0);
  }
}
@-moz-keyframes pulse {
  to {
    box-shadow: 0 0 0 45px rgba(232, 76, 61, 0);
  }
}
@-ms-keyframes pulse {
  to {
    box-shadow: 0 0 0 45px rgba(232, 76, 61, 0);
  }
}
@keyframes pulse {
  to {
    box-shadow: 0 0 0 45px rgba(232, 76, 61, 0);
  }
}
</style>
