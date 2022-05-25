<template>
  <div class="q-my-xl">
    <q-toolbar>
      <CLink v-for="link in myLinks" :key="link.title" v-bind="link" />
    </q-toolbar>
  </div>
</template>
<script>
const linksList = [
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

import CLink from "./CLink.vue";

export default {
  components: {
    CLink,
  },
  setup() {
    return {
      myLinks: linksList,
    };
  },
};
</script>
