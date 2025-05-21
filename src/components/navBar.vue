<script setup>
import { ref } from "vue";
const mobileMenuOpen = ref(false);
const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value;
};
const closeMobileMenu = () => {
  mobileMenuOpen.value = false;
};
</script>

<template>
  <div class="navbar bg-base-100 shadow-sm relative">
    <div class="navbar-start">
      <!-- Hamburger button -->
      <button
        @click="toggleMobileMenu"
        class="btn btn-ghost lg:hidden"
        aria-label="Open main menu"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-5 w-5"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h8m-8 6h16"
          />
        </svg>
      </button>
      <a class="btn btn-ghost text-xl">Exclusive Solutions <sup>Ltd</sup></a>
    </div>
    <div class="navbar-center hidden lg:flex">
      <ul class="menu menu-horizontal px-1">
        <li><a>Item 1</a></li>
        <li>
          <details>
            <summary>Parent</summary>
            <ul class="p-2">
              <li><a>Submenu 1</a></li>
              <li><a>Submenu 2</a></li>
            </ul>
          </details>
        </li>
        <li><a>Item 3</a></li>
      </ul>
    </div>
    <div class="navbar-end">
      <a class="btn">Button</a>
    </div>

    <!-- Mobile dropdown menu -->
    <transition name="fade">
      <div
        v-if="mobileMenuOpen"
        class="fixed inset-0 z-50 bg-black bg-opacity-40 lg:hidden"
        @click.self="closeMobileMenu"
      >
        <ul
          class="absolute left-0 top-16 w-full menu menu-sm bg-base-100 shadow z-50 p-2"
        >
          <li><a @click="closeMobileMenu">Item 1</a></li>
          <li>
            <a>Parent</a>
            <ul class="p-2">
              <li><a @click="closeMobileMenu">Submenu 1</a></li>
              <li><a @click="closeMobileMenu">Submenu 2</a></li>
            </ul>
          </li>
          <li><a @click="closeMobileMenu">Item 3</a></li>
        </ul>
      </div>
    </transition>
  </div>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
