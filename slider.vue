<template>
  <div class="swiper">
    <div class="swiper-wrapper">
      <div v-for="i in 6" :key="i" class="swiper-slide" :class="`slide--${i}`">
        <div class="slider-content">Slide {{ i }}</div>
      </div>
    </div>
    <!-- If pagination is needed -->
    <div class="swiper-pagination"></div>

    <!-- If navigation buttons are needed -->
    <div class="swiper-button-prev"></div>
    <div class="swiper-button-next"></div>
  </div>
</template>

<script>
// import Swiper JS
// add or remove unused modules
import { Swiper, Navigation, Pagination, Autoplay } from 'swiper'
import 'swiper/swiper-bundle.min.css'

export default {
  mounted() {
    // configure Swiper to use modules. The modules were tested with SwiperJS v6.8.4 with NuxtJS v2.15.7
    // previously it was before export default. Moved here for performance issues. Move back in case of problems.
    // add or remove unused modules
    Swiper.use([Navigation, Pagination, Autoplay])
    
    // init Swiper:
    /* eslint-disable no-unused-vars */
    const swiper = new Swiper('.swiper', {
      // Optional parameters
      // @see https://swiperjs.com/swiper-api#parameters
      direction: 'horizontal',
      loop: true,
      // remove unused modules if needed
      modules: [Navigation, Pagination, Autoplay],

      // Pagination if needed
      pagination: {
        el: '.swiper-pagination',
        type: 'bullets',
        clickable: true
      },
      // Autoplay if needed
      autoplay: {
        delay: 3000
      },
      // Navigation arrows if needed
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev'
      }
      // Configure other options. Not tested
    })
  }
}
</script>

<style scoped>
.swiper {
  height: 300px;
  overflow: hidden;
  position: relative;
  width: 500px;
}
.swiper-slide {
  align-items: center;
  display: flex;
  justify-content: center;
}
.slider-content {
  color: #000;
}
.slide--1 {
  background-color: #f1c40f;
}

.slide--2 {
  background-color: #e67e22;
}

.slide--3 {
  background-color: #e74c3c;
}

.slide--4 {
  background-color: #9b59b6;
}

.slide--5 {
  background-color: #3498db;
}

.slide--6 {
  background-color: #2ecc71;
}
</style>
