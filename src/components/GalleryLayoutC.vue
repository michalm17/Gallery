<template>
  <div class="q-pa-md">
    <q-layout
      view="lHh lpr lFf"
      container
      style="height: 400px"
      class="shadow-4 rounded-borders"
    >
      <q-header elevated>
        <q-toolbar class="bg-secondary">
          <q-toolbar-title class="absolute-center">Artist name</q-toolbar-title>
          <q-btn-dropdown stretch flat label="Artists">
            <q-list>
              <q-item-label header>Artist 1</q-item-label>
              <q-item
                v-for="n in 3"
                :key="`x.${n}`"
                clickable
                v-close-popup
                tabindex="0"
              >
                <q-item-section>
                  <q-item-label>Photos</q-item-label>
                  <q-item-label caption>born/died </q-item-label>
                </q-item-section>
              </q-item>

              <q-separator inset spaced />

              <q-item-label header>Artist 2</q-item-label>
              <q-item
                v-for="n in 3"
                :key="`x.${n}`"
                clickable
                v-close-popup
                tabindex="0"
              >
                <q-item-section>
                  <q-item-label>Photos</q-item-label>
                  <q-item-label caption>born/died </q-item-label>
                </q-item-section>
              </q-item>
            </q-list>
          </q-btn-dropdown>
        </q-toolbar>
      </q-header>

      <q-page-container>
        <q-page class="q-pa-md">
          <p v-for="n in 15" :key="n">
            <GalleryCarouselC />
          </p>
        </q-page>
      </q-page-container>
    </q-layout>
  </div>
</template>

<script>
import { ref } from "vue";
import GalleryCarouselC from "./GalleryCarouselC.vue";

export default {
  components: {
    GalleryCarouselC,
  },
  setup() {
    return {
      slide: ref(1),
      autoplay: ref(false),
      fullscreen: ref(false),
      //img fit
      fitModes: ["cover", "fill", "contain", "none", "scale-down"],
    };
  },
};
</script>

<style lang="sass" scoped>
.column > div
  padding: 10px 15px
  background: rgba(86, 61, 124, .15)
  border: 1px solid rgba(86, 61, 124, .2)

.column + .column
  margin-top: 1rem
</style>
