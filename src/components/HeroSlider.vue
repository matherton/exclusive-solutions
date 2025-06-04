<script setup>
import HeroSlides from "./HeroSlides.vue";
import Camera from "./slider-images/camera.jpg";
/* import MixingDesk from "./slider-images/mixing-desk.jpg";
import Skateboard from "./slider-images/skateboard.jpg";
import MixingDesk2 from "./slider-images/mixing-desk-2.jpg"; */

const components = {
  HeroSlides,
};
</script>
<template lang="">
  <div id="hero-slider">
    <HeroSlides :image="images[0]" />
  </div>
</template>
<script>
export default {
  name: "HeroSlider",
  data() {
    return {
      images: [
        {
          id: 0,
          src: Camera,
          title: "Camera",
          subText: "Capture moments",
        },
        {
          id: 1,
          src: "/slider-images/iphone.jpg",
          title: "iPhone",
          subText: "Capture movies",
        },
        {
          id: 2,
          src: "/slider-images/mixing-desk.jpg",
          title: "Mixing Desk",
          subText: "Mix your tracks",
        },
        {
          id: 3,
          src: "/slider-images/mixing-desk.jpg",
          title: "Mixing Desk 2",
          subText: "Mix your sound",
        },
        {
          id: 4,
          src: "/slider-images/skateboard.jpg",
          title: "Skateboard",
          subText: "Ride the streets",
        },
      ],
    };
  },
};
</script>
<style lang=""></style>
