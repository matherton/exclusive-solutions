<template lang="">
  <div id="hero-slides">
    <!-- <h2>{{ image.title }}</h2>
    <p>{{ image.subText }}</p> -->
    <div class="slideImage" :style="backgroundStyle"></div>
  </div>
</template>
<script>
export default {
  name: "HeroSlides",
  props: ["image"],
  computed: {
    backgroundStyle() {
      if (typeof this.image.src === "string") {
        return {
          backgroundImage: `url(${this.image.src})`,
        };
      } else {
        return {
          backgroundImage: `url(${require("@/slider-images/" +
            this.image.src)})`,
        };
      }
    },
  },
};
</script>
<style>
#hero-slides .slideImage {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 100vh;
  width: 100%;
}
</style>
