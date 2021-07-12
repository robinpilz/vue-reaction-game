<template>
  <div class="block" v-if="showBlock" @click="stopTimer">This is a block</div>
</template>

<script>
export default {
  name: "Block",
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      startTime: null,
      endTime: null,
      reactionTime: null,
    };
  },
  methods: {
    startTimer() {
      this.startTime = new Date();
    },
    stopTimer() {
      this.endTime = new Date();
      this.reactionTime = this.endTime - this.startTime;
      this.$emit("end", this.reactionTime);
    },
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },
};
</script>

<style>
.block {
  width: 400px;
  border-radius: 1rem;
  background: #0faf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>
