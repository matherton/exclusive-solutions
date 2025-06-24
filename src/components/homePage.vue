<script setup>
import gridColLayout from "./gridColLayout.vue";
import Carousel from "./carousel.vue";
import Hero from "./Hero.vue";
// import HeroSlider from "./HeroSlider.vue";
import HeroSlideTransition from "./HeroSlideTransition.vue";

const components = {
  gridColLayout,
  Hero,
  Carousel,
  HeroSlideTransition,
};
</script>
<template lang="">
  <!-- <HeroSlider /> -->
  <HeroSlideTransition />
  <gridColLayout />
  <Hero />
  <gridColLayout />
  <Carousel />
</template>
<script>
export default {
  name: "home",
};
</script>
<style lang=""></style>
