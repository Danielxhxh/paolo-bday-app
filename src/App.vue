<script setup>
import HelloPaolo from "./components/HelloPaolo.vue";
</script>

<template>
  <div>
    <a href="https://www.youtube.com/watch?v=dQw4w9WgXcQ" target="blank">
      <img
        src="/images/Happy-Birthday-Logo-Png.png"
        class="logo"
        alt="Vite logo"
      />
    </a>
  </div>
  <HelloPaolo />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em red);
}
</style>
