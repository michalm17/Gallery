<template>
  <div class="">
    <q-layout view="lHh Lpr lFf">
      <q-header>
        <q-toolbar-title class="text-center text-primary"
          >Gallery</q-toolbar-title
        >

        <q-img
          src="src/assets/frame.jpg"
          width="100%"
          height="150%"
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

        <q-btn class="row" v-else @click="viewWindow = !viewWindow" to="/">
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
.router-view {
  z-index: 1;
}

.header-image {
  z-index: -1;
}
</style>
