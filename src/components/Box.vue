<template>
  <div v-if="showBox" class="box">Click</div>
</template>

<script>
export default {
  props: ["timerDelay"],
  data() {
    return {
      boxColor: this.color,
      showBox: false,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBox = true;
    }, this.timerDelay);
  },
  updated() {
    console.log("zrobione");
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
}
</style>
