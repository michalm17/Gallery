<!-- eslint-disable prettier/prettier -->
<template>
  <swiper
    :effect="'coverflow'"
    :grabCursor="true"
    :centeredSlides="true"
    :slidesPerView="'auto'"
    :coverflowEffect="{
      rotate: 25,
      stretch: 20,
      depth: 260,
      modifier: 3,
      slideShadows: true,
    }"
    :pagination="false"
    :modules="modules"
    class="mySwiper"
  >
    <swiper-slide><img v-bind:src="images[0].src" /></swiper-slide
    ><swiper-slide><img v-bind:src="images[0].src" /></swiper-slide
    ><swiper-slide><img v-bind:src="images[1].src" /></swiper-slide
    ><swiper-slide><img v-bind:src="images[2].src" /></swiper-slide>
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
      images: [
        {
          src: "src/assets/LeonBakst1" + ".png",
          name: "some text",
          age: "1234",
        },
        {
          src: "src/assets/LeonBakst2" + ".jpg",
          name: "some text",

          age: "1234",
        },
        {
          src: "src/assets/LeonBakst3" + ".jpg",
          name: "some text",

          age: "1234",
        },
      ],
    };
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
  width: 300px;
  height: 300px;
}

.swiper-slide img {
  display: block;
  width: 100%;
}
</style>
