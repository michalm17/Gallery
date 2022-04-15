<template>
  <q-page class="center">
    <CarouselC></CarouselC>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import CarouselC from "src/components/CarouselC.vue";

export default defineComponent({
  name: "IndexPage",
  components: { CarouselC },
});
</script>
