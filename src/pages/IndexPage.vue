<template>
  <q-page class="center">
    <GalleryLayoutC />
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import GalleryLayoutC from "src/components/GalleryLayoutC.vue";

export default defineComponent({
  name: "IndexPage",
  components: { GalleryLayoutC },
});
</script>
