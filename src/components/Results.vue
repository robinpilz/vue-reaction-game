<template>
  <div>Reaction time: {{ reactionTime }} ms</div>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
  name: "Results",
  props: ["reactionTime"],
  components: {},
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.reactionTime < 250) {
      this.rank = "Ninja Fingers";
    } else if (this.reactionTime < 400) {
      this.rank = "Rocket Reflexes";
    } else {
      this.rank = "Snail pace...";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4rem;
  color: #0faf87;
  font-weight: bold;
}
</style>
