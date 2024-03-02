<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

// import required modules
import { Pagination } from "swiper/modules";

// Import Swiper styles
import "swiper/css";
import "swiper/css/pagination";
// import "./style.css";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const photos = [
      "photo_1.jpg",
      "photo_2.jpg",
      "photo_3.jpg",
      "photo_4.jpg",
      "photo_5.jpg",
      "photo_6.jpg",
      "photo_7.jpg",
      "photo_8.jpg",
    ];
    return {
      modules: [Pagination],
      photos,
    };
  },
};
</script>

<template>
  <main class="container">
    <h1>Photo Gallery</h1>
    <Swiper
      :loop="true"
      :spaceBetween="30"
      :pagination="{
        clickable: true,
        dynamicBullets: true,
      }"
      :modules="modules"
      class="swiper"
    >
      <SwiperSlide v-for="photo in photos" :key="photo">
        <img :src="`${photo}`" alt="" />
      </SwiperSlide>
    </Swiper>
  </main>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Rubik:ital,wght@0,300..900;1,300..900&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Rubik", sans-serif;
}

body {
  background-color: #b2b2c6;
  color: aliceblue;
}

.container {
  margin: 0 auto;
  padding: 50px 0;
  max-width: 1000px;
}

.swiper {
  width: 800px;
  height: 600px;
  overflow: visible;
}

.swiper-slide img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.swiper-pagination-bullets {
  width: 12px;
  height: 12px;
}
</style>
