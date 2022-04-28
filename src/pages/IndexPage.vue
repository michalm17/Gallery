<template>
  <q-page class="center q-pa-md">
    <GalleryC />
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import GalleryC from "src/components/GalleryC.vue";

import AboutWindow from "../components/AboutWindow.vue";

export default defineComponent({
  name: "IndexPage",
  components: { GalleryC },
});
</script>
