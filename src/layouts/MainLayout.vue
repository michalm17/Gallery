<template>
  <div class="">
    <q-layout view="2hh Lpr lFf">
      <q-header>
        <q-toolbar-title class="text-center text-dark"
          >Gallery dropdown</q-toolbar-title
        >

        <q-img
          src="src/assets/Frame/frame.png"
          width="100px"
          height="100px"
          class="header-image absolute-top-right"
          style="transform: rotateY(180deg)"
        >
        </q-img>
        <q-img
          src="src/assets/Frame/frame.png"
          width="100px"
          height="100px"
          class="header-image absolute-top-left"
          style=""
        >
        </q-img>
      </q-header>

      <q-btn
        round
        class="row"
        padding="35px"
        v-if="viewWindow"
        @click="viewWindow = !viewWindow"
        to="about"
        unelevated
      >
        <q-icon name="school" color="dark" size="30px" />
      </q-btn>

      <q-btn class="row" v-else @click="viewWindow = !viewWindow" to="/">
        <q-icon name="brush" color="dark" size="60px" />
      </q-btn>

      <q-page-container>
        <q-page padding>
          <router-view />
        </q-page>
      </q-page-container>
    </q-layout>
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";

const view = "gallery";
export default defineComponent({
  name: "MainLayout",

  components: {},

  data() {
    return {
      viewWindow: true,
    };
  },
});
</script>

<style lang="scss">
.router-view {
  z-index: 1;
}
//add a class or id for header image
.header-image {
  z-index: -1;
}
</style>
