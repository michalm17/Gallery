<!-- eslint-disable prettier/prettier -->
<template>
  <swiper
    :effect="'coverflow'"
    :grabCursor="true"
    :centeredSlides="true"
    :slidesPerView="'auto'"
    :coverflowEffect="{
      rotate: 15,
      stretch: 5,
      depth: 5,
      modifier: 3,
      slideShadows: false,
    }"
    :pagination="false"
    :modules="modules"
    :loop="true"
    class="mySwiper"
  >
    <swiper-slide><img v-bind:src="artist[0].src[0]" /></swiper-slide
    ><swiper-slide><img v-bind:src="artist[0].src[1]" /></swiper-slide
    ><swiper-slide><img v-bind:src="artist[0].src[2]" /></swiper-slide
    ><swiper-slide><img v-bind:src="artist[1].src[0]" /></swiper-slide>
    <swiper-slide><img v-bind:src="artist[1].src[1]" /></swiper-slide>
  </swiper>
</template>
<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";

import "swiper/css/effect-coverflow";
import "swiper/css/pagination";

// import required modules
import { EffectCoverflow, Pagination } from "swiper";

// Artist name variable, for changing a routing site and contain of swiper
let artistName = "Leon Bakst";
let imageNumber = 1;
let srcCode = "src/assets/" + artistName + "/" + imageNumber + ".jpg";
export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [EffectCoverflow, Pagination],
    };
  },
  data() {
    return {
      artist: [
        {
          name: "Leon Bakst",
          age: "1234",
          src: [
            srcCode,
            "src/assets/Leon Bakst/" + "2" + ".jpg",
            "src/assets/Leon Bakst/" + "3" + ".jpg",
          ],
        },
        {
          name: "Utagawa Hiroshige",
          age: "1234",
          src: [
            "src/assets/Utagawa Hiroshige/" + "1" + ".jpg",
            "src/assets/Utagawa Hiroshige/" + "2" + ".jpg",
          ],
        },
        {
          name: "some text",
          age: "1234",
          src: "src/assets/Name Surname/" + "number" + ".jpg",
        },
      ],
    };
  },
  methods: {
    displayImages() {
      //if (imageNumber < number
    },
  },
};
</script>
<style scoped>
#app {
  height: 100%;
}
html,
body {
  position: relative;
  height: 100%;
}

body {
  background: #eee;
  font-family: Helvetica Neue, Helvetica, Arial, sans-serif;
  font-size: 14px;
  color: #000;
  margin: 0;
  padding: 0;
}

.swiper {
  width: 100%;
  padding-top: 50px;
  padding-bottom: 50px;
}

.swiper-slide {
  background-position: center;
  background-size: cover;
  width: auto;
  height: 300px;
}

.swiper-slide img {
  margin: auto;
  display: block;
  width: auto;
  height: 300px;
}
</style>
