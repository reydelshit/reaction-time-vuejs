<template>
  <div class="block" v-if="showBlock" @click="stop">
      <span>stop me</span>
  </div>
</template>

<script>

export default {
    name: 'Block',
    components: {},
    props: ['delay'],

    data(){
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0
        }
    },
    methods: {
        start() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)
    },
        stop(){
            clearInterval(this.timer)
            this.$emit('end', this.reactionTime)
        }
    },
    mounted(){
      setTimeout(() => {
        this.showBlock = true
        this.start()
      }, this.delay)
    }
}
</script>

<style>
.block{
    width: 400px;
    background: aqua;
    padding: 5em;
    margin: 2rem auto;
    border-radius: 5px;
    cursor: pointer;

}
</style>