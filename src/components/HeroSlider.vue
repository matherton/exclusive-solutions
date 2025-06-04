<script setup>
import HeroSlides from "./HeroSlides.vue";
import cameraImage from "@/slider-images/camera.jpg?url";
import iphoneImage from "@/slider-images/iphone.jpg?url";
import mixingDeskImage from "@/slider-images/mixing-desk.jpg?url";
import mixingDesk2Image from "@/slider-images/mixing-desk2.jpg?url";
import skateboardImage from "@/slider-images/skateboard.jpg?url";

const components = {
  HeroSlides,
};
</script>
<template lang="">
  <div id="hero-slider">
    <HeroSlides :image="images[4]" />
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
          src: cameraImage,
          title: "Camera",
          subText: "Capture moments",
        },
        {
          id: 1,
          src: iphoneImage,
          title: "iPhone",
          subText: "Capture movies",
        },
        {
          id: 2,
          src: mixingDeskImage,
          title: "Mixing Desk",
          subText: "Mix your tracks",
        },
        {
          id: 3,
          src: mixingDesk2Image,
          title: "Mixing Desk 2",
          subText: "Mix your sound",
        },
        {
          id: 4,
          src: skateboardImage,
          title: "Skateboard",
          subText: "Ride the streets",
        },
      ],
    };
  },
  mounted() {
    console.log(this.images);
  },
};
</script>
<style lang=""></style>
