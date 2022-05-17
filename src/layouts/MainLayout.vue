<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar-title class="text-center">Gallery</q-toolbar-title>

      <q-btn
        class="row justify-center"
        v-if="viewWindow"
        @click="viewWindow = !viewWindow"
        icon="school"
        to="about"
      />
      <q-btn
        class="row justify-center"
        v-else
        @click="viewWindow = !viewWindow"
        icon="brush"
        to="/"
      />

      <q-img src="src/assets/frame.jpg" class="header-image absolute-top" />
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
    <q-footer reveal:true bordered:true> Abc</q-footer>
  </q-layout>
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
.header-image {
  height: 100%;
  z-index: -1;
}
</style>
