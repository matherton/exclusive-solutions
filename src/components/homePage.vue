<script setup>
import gridColLayout from "./gridColLayout.vue";
import Carousel from "./carousel.vue";
import Hero from "./Hero.vue";
// import HeroSlider from "./HeroSlider.vue";
import HeroSlideTransition from "./HeroSlideTransition.vue";
import Divider from "./divider.vue";

const components = {
  gridColLayout,
  Hero,
  Carousel,
  HeroSlideTransition,
  Divider,
};
</script>
<template lang="">
  <!-- <HeroSlider /> -->
  <HeroSlideTransition />
  <gridColLayout />
  <Hero />
  <Divider />
  <Carousel />
</template>
<script>
export default {
  name: "home",
};
</script>
<style lang=""></style>
