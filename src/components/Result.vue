<template>
  <p>Your reaction time - {{ reactionTime }}ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  props: ["reactionTime"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.reactionTime < 250) {
      this.rank = "You are really fast";
    } else if (this.reactionTime < 400) {
      this.rank = "Preety fast";
    } else {
      this.rank = "You are slower, than I thought...";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4rem;
  color: green;
  font-weight: bold;
}
</style>
