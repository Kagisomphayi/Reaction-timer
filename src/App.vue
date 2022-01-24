<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isplaying">Play!!!</button>
  <Block v-if="isplaying" :delay="delay" />
</template>

<script>
import Block from "./components/Block"

export default {
  name: "App",
  components: { Block },

  data() {
    return {
      isplaying: false,
      delay: null,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isplaying = true;
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444444;
  margin-top: 60px;
}
</style>
