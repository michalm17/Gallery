<template>
  <div class="q-pa-md doc-container">
    <div class="column">
      <div class="col">
        1 of 3

        <q-carousel
          :height="windowHeight"
          swipeable
          animated
          :autoplay="autoplay"
          v-model="slide"
          ref="carousel"
          infinite
          v-model:fullscreen="fullscreen"
        >
          <q-carousel-slide
            :name="1"
            class="inline-flex"
            img-src="https://www.printsandfineart.co.uk/previews/none/none/none/800/12-18-I/16-22-I/GM4577.jpg"
          />
          <q-carousel-slide :name="2" class="flex flex-center"
          img-src=src/assets/TheSleepingBeautyWolf.jpg />
          <q-carousel-slide :name="3" img-src="" />
          <q-carousel-slide :name="4" img-src="" />

          <template v-slot:control>
            <q-carousel-control
              position="bottom-right"
              :offset="[18, 18]"
              class="text-white rounded-borders"
              style="background: rgba(0, 0, 0, 0); padding: 1px 1px"
            >
              <q-btn
                push
                round
                dense
                color="secondary"
                text-color="primary"
                :icon="fullscreen ? 'fullscreen_exit' : 'fullscreen'"
                @click="fullscreen = !fullscreen"
              />
            </q-carousel-control>

            <q-carousel-control
              position="bottom-right"
              :offset="[18, 18]"
              class="q-gutter-xs"
            >
            </q-carousel-control>
          </template>
        </q-carousel>
      </div>
      <div class="col-5">
        2 of 3
        <q-btn
          push
          round
          dense
          color="orange"
          text-color="black"
          icon="arrow_left"
          @click="$refs.carousel.previous()"
        />
        <q-toggle
          dense
          dark
          color="orange"
          v-model="autoplay"
          label="Auto Play"
        />

        <q-btn
          push
          round
          dense
          color="orange"
          text-color="black"
          icon="arrow_right"
          @click="$refs.carousel.next()"
        />
      </div>
      <div class="col-6">
        3 of 3
        <p>Opis</p>
      </div>
    </div>
  </div>
</template>
<script>
import { ref } from "vue";

export default {
  created() {
    this.windowHeight = window.innerHeight + "px";
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
  padding: 25px 40px
  background: rgba(100, 100, 124, .15)
  border: 1px rgba(8, 6, 12, .2)
</style>
