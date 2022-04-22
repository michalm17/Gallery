<template>
  <q-page class="center q-pa-md">
    <GalleryC />
    <GalleryCarouselC />
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import GalleryC from "src/components/GalleryC.vue";
import GalleryCarouselC from "src/components/GalleryCarouselC.vue";

export default defineComponent({
  name: "IndexPage",
  components: { GalleryC, GalleryCarouselC },
});
</script>
