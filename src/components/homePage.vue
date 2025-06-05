<script setup>
import gridColLayout from "./gridColLayout.vue";
import Carousel from "./carousel.vue";
import Hero from "./Hero.vue";
import HeroSlider from "./HeroSlider.vue";

const components = {
  gridColLayout,
  Hero,
  Carousel,
  HeroSlider,
};
</script>
<template lang="">
  <HeroSlider />
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
