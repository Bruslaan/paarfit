<template>
  <div>
    <div class="d-flex justify-center">
      <v-btn text @click="$router.push({name:'home'})">Abbruch</v-btn>
    </div>
    <div class style="height:80vh">
      <transition-group
        appear
        appear-active-class="animated fadeInUp"
        name="custom-classes-transition"
        :enter-active-class="isNext ? 'animated fadeInUp' : 'animated fadeInDown'"
        :leave-active-class="isNext ? 'animated fadeOutUp' : 'animated fadeOutDown'"
        mode="out-in"
      >
        <v-card v-if="menu==1" class="row" key="1" outlined>
          <div class="d-flex justify-center align-center">Test</div>
        </v-card>

        <v-card v-if="menu==2" class="row" key="2" outlined>
          <div class="d-flex justify-center align-center">Test2</div>
        </v-card>
      </transition-group>
    </div>
    <div class="d-flex justify-center align-center bottom_nav">
      <button @click="prev" class="prev">Zurück</button>
      <button @click="next" class="next">Weiter</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menu: 1,
      isNext: true
    };
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
.row {
  /* Slide Position */
  position: absolute;
  height: 70vh;
  width: 90vh;
  align-content: center;
  margin: auto;
  left: 0;
  right: 0;
  /* Border & BG */
  border: 1px dashed #009688;
  border-radius: 5px;

  /* Text */
  text-align: center;
  text-transform: capitalize;
  font-weight: bold;
  font-size: 25px;
  color: #009688;
  line-height: 200px;
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
  bottom: 5px;
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