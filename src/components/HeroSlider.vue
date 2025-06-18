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
  <div class="hero-slider-container">
    <div id="hero-slider">
      <div class="arrowRight" @click="move">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-12 w-12"
          fill="white"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="green"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M10 4l6 6-6 6z"
          />
        </svg>
      </div>

      <HeroSlides :image="images[chooseImage]" />
      <div class="arrowLeft" @click="move">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-12 w-12"
          fill="white"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="green"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M14 4l-6 6 6 6z"
          />
        </svg>
      </div>
    </div>
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
      chooseImage: 0,
    };
  },
  methods: {
    move() {
      if (this.chooseImage >= this.images.length - 1) {
        this.chooseImage = 0; // Reset to first image
      } else {
        this.chooseImage++; // Move to next image
      }
      // Uncomment the line below to log the current image index
      // console.log("Current image index:", this.chooseImage);
      // Uncomment the line below to log the current image title
      // console.log("Current image title:", this.images[this.chooseImage].title);
      // Uncomment the line below to log the current image subText
      // console.log("Current image subText:", this.images[this.chooseImage].subText);
      // Uncomment the line below to log the current image src
      // console.log("Current image src:", this.images[this.chooseImage].src);
      // Uncomment the line below to log the current image id
      // console.log("Current image id:", this.images[this.chooseImage].id);
    },
  },
  created() {
    setInterval(() => {
      this.move();
    }, 4000); // Change image every 4 seconds
  },
};
</script>
<style lang=""></style>
