<template lang="">
  <div
    class="grid grid-cols-1 md:grid-cols-3 xl:grid-cols-6 gap-4 m-2 bg-white text-black rounded"
  >
    <div class="border">01</div>
    <div class="border">02</div>
    <div class="border">03</div>
    <div class="border">04</div>
    <div class="border">05</div>
    <div class="border">06</div>
  </div>
</template>
<script>
export default {
  name: "gridColLayout",
  props: {
    col: {
      type: Number,
      default: 1,
    },
  },
  data() {
    return {
      colClass: "",
    };
  },
};
</script>
<style lang=""></style>
