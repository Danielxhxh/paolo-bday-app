<template>
  <div id="background" :style="{ backgroundColor: color }"></div>
  <div>
    <audio ref="audio" :src="audioSrc" />

    <div v-show="pressed">
      <img
        src="images/cool_paolo_pic.png"
        alt="cool paolo pic"
        style="height: 350px"
      />
      <br />
      <h1>Paoletto</h1>
    </div>

    <button v-show="!pressed" type="button" @click="pressedButton()">
      Press me bro
    </button>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

let pressed = ref(false);
let color = ref("rgb(100, 7, 57)");
let intervalId = null;
let audioSrc = "/audio/bangarang.mp3";
let audioRef = ref(null);

onMounted(() => {
  audioRef.value = audioRef.value || new Audio(audioSrc);
  audioRef.value.loop = true;
});

function pressedButton() {
  pressed.value = true;
  audioRef.value.play();

  intervalId = setInterval(() => {
    color.value = `rgb(${getRandomInt(0, 255)}, ${getRandomInt(
      0,
      255
    )}, ${getRandomInt(0, 255)})`;

    function getRandomInt(min, max) {
      return Math.floor(Math.random() * (max - min + 1) + min);
    }
  }, 300);
}
</script>

<style>
#background {
  z-index: -1;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  position: absolute;
}
</style>
