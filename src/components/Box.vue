<template>
  <div v-if="showBox" class="box" @click="stopTimer">Click</div>
</template>

<script>
export default {
  props: ["timerDelay"],
  data() {
    return {
      showBox: false,
      timer: null,
      reactionTime: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBox = true;
      this.startTimer();
    }, this.timerDelay);
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      this.$emit("endTimer", this.reactionTime);
    },
  },
};
</script>

<style>
.box {
  width: 500px;
  height: 250px;
  background-color: crimson;
  border-radius: 20px;
  margin-bottom: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 0px;
  color: #fff;
  font-weight: bold;
  text-transform: uppercase;
  cursor: pointer;
}
</style>
