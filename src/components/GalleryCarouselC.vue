<template>
  <div class="q-mx-lg">
    <div class="column">
      <div>
        <q-carousel
          swipeable
          animated
          :autoplay="autoplay"
          v-model="slide"
          ref="carousel"
          infinite
          v-model:fullscreen="fullscreen"
        >
          <q-carousel-slide :name="1">
            <div class="flex flex-center">
              <q-img src="src/assets/LeonBakst2.jpg" />
            </div>
          </q-carousel-slide>
          <q-carousel-slide :name="2">
            <div class="flex flex-center">
              <q-img src="src/assets/TheSleepingBeautyWolf.jpg" />
            </div>
          </q-carousel-slide>
          <q-carousel-slide :name="3">
            <div class="flex flex-center">
              <q-img src="src/assets/LeonBakst1.png" />
            </div>
          </q-carousel-slide>

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
                color="primary"
                text-color="secondary"
                :icon="fullscreen ? 'fullscreen_exit' : 'fullscreen'"
                @click="fullscreen = !fullscreen"
              />
            </q-carousel-control>

            <q-carousel-control
              position="bottom-right"
              :offset="[18, 18]"
              class="q-gutter"
            >
            </q-carousel-control>
          </template>
        </q-carousel>
      </div>

      <div>
        2 of 3
        <q-btn
          push
          round
          dense
          color="primary"
          text-color="black"
          icon="arrow_left"
          @click="$refs.carousel.previous()"
        />
        <q-toggle
          dense
          dark
          color="primary"
          v-model="autoplay"
          label="Auto Play"
        />

        <q-btn
          push
          round
          dense
          color="primary"
          text-color="black"
          icon="arrow_right"
          @click="$refs.carousel.next()"
        />
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
.q-img
  width: 250px
  box-shadow: 0 4px 10px 0 rgba(0, 20, 0, 20), 0 6px 20px 0 rgba(0, 0, 0, 0.19)
</style>
