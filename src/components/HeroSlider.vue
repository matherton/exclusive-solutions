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
    <div class="hero-slider">
      <div class="arrowRight" @click="moveRight">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-24 w-24"
          fill="white"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="white"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M10 4l6 6-6 6z"
          />
        </svg>
      </div>

      <HeroSlides :image="images[chooseImage]" />
      <div class="arrowLeft" @click="moveLeft">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-24 w-24"
          fill="white"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="white"
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
    },
    moveRight() {
      if (this.chooseImage >= this.images.length - 1) {
        this.chooseImage = 0; // Reset to first image
      } else {
        this.chooseImage++; // Move to next image
      }
    },
    moveLeft() {
      if (this.chooseImage === 0) {
        this.chooseImage = this.images.length - 1;
      } else {
        this.chooseImage--;
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
<style>
.hero-slider {
  position: relative;
}

.arrowRight {
  position: absolute;
  top: 50%;
  right: 0;
  transform: translateY(-50%);
  z-index: 10; /* Ensure the arrow is above the slides */
  cursor: pointer;
}

.arrowLeft {
  position: absolute;
  top: 50%;
  left: 0;
  transform: translateY(-50%);
  z-index: 10; /* Ensure the arrow is above the slides */
  cursor: pointer;
}
</style>
