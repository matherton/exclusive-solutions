<template lang="">
  <div class="drawer">
    <input id="my-drawer" type="checkbox" class="drawer-toggle" />
    <div class="drawer-content" style="margin: 0 auto; max-width: 1200px">
      <!-- Page content here -->
      <label for="my-drawer" class="btn drawer-button">Open drawer</label>
    </div>
    <div class="drawer-side">
      <label
        for="my-drawer"
        aria-label="close sidebar"
        class="drawer-overlay"
      ></label>
      <ul class="menu bg-base-200 text-base-content min-h-full w-80 p-4">
        <!-- Sidebar content here -->
        <li><a>Sidebar Item 1</a></li>
        <li><a>Sidebar Item 2</a></li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  name: "leftDrawer",
};
</script>
<style lang=""></style>
