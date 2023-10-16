<template>
  <div class="home">
    <Carousel
      :navigation="true"
      :pagination="true"
      :startAutoPlay="true"
      :timeout="5000"
      class="carousel"
      v-slot="{ currentSlide }"
    >
      <Slide v-for="(slide, index) in carouselSlides" :key="index">
        <div v-show="currentSlide === index + 1" class="slide-info">
          <img :src="slide" alt="" />
        </div>
      </Slide>
    </Carousel>
  </div>
</template>

<script setup>
import Carousel from "../components/Carousel.vue";
import Slide from "../components/Slide.vue";
import hondaImage from "../../img/honda.avif";
import honda2Image from "../../img/honda2.avif";
import honda3Image from "../../img/honda3.avif";

const carouselSlides = [hondaImage, honda2Image, honda3Image];
</script>

<style lang="scss" scoped>
.carousel {
  position: relative;
  max-height: 100vh;
  height: 100vh;

  .slide-info {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    max-height: 100%;
    height: 100%;

    img {
      min-width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
}
</style>
