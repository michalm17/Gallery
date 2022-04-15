<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <CLink v-for="link in essentialLinks" :key="link.title" v-bind="link" />

        <q-toolbar-title></q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
    <q-footer reveal:true bordered:true> Abc</q-footer>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import CLink from "components/CLink.vue";

const linksList = [
  {
    title: "Gallery",
    caption: "Main Page",
    icon: "alarm",
    link: "",
  },
  {
    title: "About",
    caption: "Little something",
    icon: "alarm",
    link: "",
  },
  {
    title: "Github",
    caption: "github.com/michalm17",
    icon: "code",
    link: "https://github.com/michalm17",
  },

  {
    title: "Facebook",
    caption: "Michał Matysiak",
    icon: "public",
    link: "https://www.facebook.com/profile.php?id=100066908805765",
  },
];

export default defineComponent({
  name: "MainLayout",

  components: {
    CLink,
  },

  setup() {
    return {
      essentialLinks: linksList,
    };
  },
});
</script>
