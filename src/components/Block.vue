<template>
  <div class="block" v-if="showBlock" @click="stopTimer">Click</div>
</template>

<script>
export default {
  props: ["delay"],

  data() {
    return {
      showBlock: false,
      timer:null,
      reactionTime: 0
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer()
    }, this.delay);
  },
  methods: {
    startTimer() {
this.timer=setInterval(() => {
    this.reactionTime +=10
},10)

    },

    stopTimer(){
        clearInterval(this.timer)
        this.$emit('end',this.reactionTime)
    }
  },
};
</script>

<style>
.block {
  width: 400px;
  border-radius: 15px;
  background:darkmagenta;
  color: cornsilk;
  padding: 100px 0;
  margin: 50px auto;
  text-align: center;
}
</style>
