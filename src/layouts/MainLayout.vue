<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar-title class="text-center">Gallery</q-toolbar-title>

      <q-btn v-if="viewWindow" @click="viewWindow = !viewWindow">About</q-btn>
      <q-btn v-else @click="viewWindow = !viewWindow">Gallery</q-btn>
    </q-header>

    <q-page-container>
      <router-view v-if="viewWindow" />
      <AboutWindow v-else />
    </q-page-container>
    <q-footer reveal:true bordered:true> Abc</q-footer>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import AboutWindow from "src/components/AboutWindow.vue";

const view = "gallery";
export default defineComponent({
  name: "MainLayout",

  components: { AboutWindow },

  data() {
    return {
      viewWindow: true,
    };
  },
});
</script>
