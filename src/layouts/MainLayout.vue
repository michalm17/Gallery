<template>
  <div class="q-pa-md q-gutter-y-sm">
    <q-layout view="lHh Lpr lFf">
      <q-header elevated>
        <q-toolbar-title class="text-center text-primary"
          >Gallery</q-toolbar-title
        >

        <q-img
          src="src/assets/frame.jpg"
          :ratio="4 / 3"
          width="auto"
          height="100px"
          class="header-image absolute-top"
        >
        </q-img>

        <q-btn
          class="row"
          v-if="viewWindow"
          @click="viewWindow = !viewWindow"
          to="about"
        >
          <q-icon name="school" color="primary" size="30px" />
        </q-btn>

        <q-btn
          class="row justify-center"
          v-else
          @click="viewWindow = !viewWindow"
          to="/"
        >
          <q-icon name="brush" color="primary" size="30px" />
        </q-btn>
      </q-header>

      <q-page-container>
        <router-view />
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
.q-img {
  padding-top: 0 !important;
}

.router-view {
  z-index: 1;
}

.header-image {
  z-index: -1;
}
</style>
