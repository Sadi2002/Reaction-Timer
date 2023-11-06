<template>
  <h1>Reaction Timer App</h1>
  <Box :class="boxColor" :timerDelay="delay" v-if="isPlaying" />
  <button class="start" :disabled="isPlaying" @click="start">Start</button>
</template>

<script>
import Box from "./components/Box.vue";
export default {
  name: "App",
  components: { Box },
  data() {
    return {
      isPlaying: false,
      delay: null,
      boxColor: "crimson",
    };
  },
  methods: {
    start() {
      (this.isPlaying = true), (this.delay = 2000 + Math.random() * 5000);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
h1 {
  font-size: 40px;
  margin-bottom: 50px;
}
.start {
  width: 200px;
  height: 50px;
  border-radius: 10px;
  background-color: rgb(219, 208, 188);
  cursor: pointer;
  border: 1px solid grey;
  font-size: 20px;
  text-transform: uppercase;
  transition: all 0.5s;
}
.start:hover {
  background-color: green;
  color: #fff;
}
</style>
