<template>
  <div>
    <b-button
      id="drum-parts"
      v-bind:class="{ active: isActive }"
      @click="playSound(fileName, volume)"
      >{{ name }}</b-button
    >
  </div>
</template>

<script>
import { Howl } from "howler";

export default {
  data() {
    return {
      isActive: false,
    };
  },
  props: {
    name: {
      type: String,
      required: true,
    },
    fileName: {
      type: String,
      required: true,
    },
    volume: {
      type: String,
      required: true,
    },
    keyBind: {
      type: String,
      required: true,
    },
  },
  created() {
    window.addEventListener("keydown", this.handleKeyDown);
    window.addEventListener("keyup", this.loseFocus);
  },
  beforeDestroy() {
    window.removeEventListener("keydown", this.handleKeyDown);
    window.addEventListener("keyup", this.loseFocus);
  },
  methods: {
    playSound(fileName, volume) {
      const sound = new Howl({
        src: require("../assets/audio/" + fileName),
        volume: volume / 10,
        html5: true,
      });
      sound.play();
    },
    handleKeyDown(event) {
      if (event.code === this.keyBind) {
        this.playSound(this.fileName, this.volume);
        this.isActive = true;
      }
      return;
    },
    loseFocus() {
      this.isActive = false;
    },
  },
};
</script>

<style>
@import "../assets/styles/main.scss";
</style>
