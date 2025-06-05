<template lang="">
  <transition-group name="fade" mode="out-in" tag="div" id="hero-slides">
    <div class="slideImage" :style="backgroundStyle" key:="image.id">
      <div class="slideTitle">
        <h2>{{ image.title }}</h2>

        <p>{{ image.subText }}</p>
      </div>
    </div>
  </transition-group>
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
  height: 100vh;
  width: 100%;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
#hero-slides .slideImage .slideTitle {
  color: white;
  display: flex;
  flex-direction: column;
  font-size: 2rem;
  font-weight: bold;
  height: 100vh;
  align-items: center;
  justify-content: center;
}
#hero-slides .slideTitle h2 {
  font-size: 3rem;
  margin-bottom: 1rem;
}
#hero-slides .slideTitle p {
  font-size: 1.5rem;
}

.fade-enter-active {
  animation-name: fadeenter;
  animation-duration: 1s;
  animation-iteration-count: 1;
}
.fade-move {
  transition: all 1s ease;
}
.fade-leave-active {
  animation-name: fadeleave;
  animation-duration: 1s;
  animation-iteration-count: 1;
  position:absolute;
}
@keyframes fadeenter {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@keyframes fadeleave {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
</style>
