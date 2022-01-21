<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
      Click Me
  </div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
      return {
        showBlock: false,
        timer: null,
        reactionTime: 0
      }
    },
    mounted() {
      setTimeout(() => {
        this.showBlock = true;
        this.startTimer();
      }, this.delay);  
    },
    methods: {
      startTimer() {
        this.timer = setInterval(() => {
            this.reactionTime += 10
        }, 10);  
      },
      stopTimer() {
          clearInterval(this.timer);
          this.$emit('done', this.reactionTime);
      }  
    }
}
</script>

<style>
    .block {
        width: 30px;
        border-radius: 200px;
        background: #000000;
        color: rgb(0, 195, 255);
        text-align: center;
        padding: 200px;
        margin: 10px auto;
        box-shadow: rgb(0, 195, 255);
    }
</style>