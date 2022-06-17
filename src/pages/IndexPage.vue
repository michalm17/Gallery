<template>
  <q-page class="center q-pa-md">
    <GalleryCarouselC />
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import GalleryCarouselC from "src/components/GalleryCarouselC.vue";

export default defineComponent({
  name: "IndexPage",
  components: { GalleryCarouselC },
});
</script>
