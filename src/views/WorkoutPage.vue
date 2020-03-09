<template>
  <div>
    <!-- <div class="d-flex justify-center">
      <v-btn text @click="$router.push({name:'home'})">Abbruch</v-btn>
    </div>-->

    <div style="height:80vh">
      <div v-for="(card, index) in 3" :key="index">
        <transition
          v-if="index==menu"
          appear
          appear-active-class="animated fadeInUp"
          name="custom-classes-transition"
          :enter-active-class="isNext ? 'animated fadeInUp' : 'animated fadeInDown'"
          :leave-active-class="isNext ? 'animated fadeOutUp' : 'animated fadeOutDown'"
          mode="out-in"
        >
          <v-card class="customrow" outlined>
            <video width="100%" controls>
              <source src="movie.mp4" type="video/mp4" />
              <source src="movie.ogg" type="video/ogg" />Your browser does not support the video tag.
            </video>
            <v-card-title>Übung Name {{index+1}}/3</v-card-title>

            <v-card-text>
              <div class="my-4 subtitle-1">Hier BLabla</div>

              <div>Viel BLABLA</div>
            </v-card-text>
          </v-card>
        </transition>
      </div>
    </div>
    <div class="d-flex justify-center align-center bottom_nav">
      <button @click="prev" class="prev">Zurück</button>
      <v-progress-circular :size="50" :value="progress">{{ progressDiscret }}</v-progress-circular>
      <button @click="next" class="next">Weiter</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menu: 0,
      isNext: true
    };
  },

  computed: {
    progress() {
      return (this.menu / 3) * 100;
    },
    progressDiscret(){
      return this.menu + "/"+3
    }
  },
  methods: {
    next() {
      this.isNext = true;
      this.menu = this.menu + 1;
    },
    prev() {
      this.isNext = false;
      this.menu = this.menu - 1;
    }
  }
};
</script>

<style scoped>
.bottom_nav {
  position: sticky;
  bottom: 0;
}
.customrow {
  /* Slide Position */
  position: absolute;
  margin: auto;
  left: 0;
  right: 0;
  height: 70vh;
  width: 90vh;
}
.nav {
  background-color: #fbe9e7;
  position: absolute;
  bottom: 0;
  left: 0;
  height: 60px;
  width: 100%;
  border-top: 1px dashed #ff5722;
  color: #ff5722;
}
.prev {
  right: Calc(50% + 65px);
}
.next {
  right: Calc(50% - 145px);
}
.next,
.prev {
  position: absolute;
  bottom: 0px;
  width: 70px;
  text-align: center;
  padding: 7px;
  cursor: pointer;
  border-radius: 5px;
  border: 1px dashed #ff5722;
  background-color: white;
  color: #ff5722;
  box-shadow: 1px 1px 1px 0px #9e9e9e;
}
</style>