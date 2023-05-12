<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    click me
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
        this.showBlock = true
        this.startTimer()
    }, this.delay)
},
methods: {
    startTimer() {
        this.timer = setInterval( () => {
            this.reactionTime += 10
        }, 10)
    },
    stopTimer() {
        clearInterval(this.timer)
        console.log(this.reactionTime)
        this.$emit('end', this.reactionTime)
    },
}
}
</script>

<style>
.block {
width: 400px;
height: 400px;
background: linear-gradient(to bottom, #000000, #0faf87);
border-radius: 50%;
box-shadow: 0 0 50px 10px #0faf87;
text-align: center;
font-size: 36px;
color: white;
display: flex;
align-items: center;
justify-content: center;
margin: 40px auto;
position: relative;
overflow: hidden;
transform-style: preserve-3d;
transition: all 0.5s ease-in-out;
}

.block:hover {
transform: scale(1.2) rotateY(360deg);
}

.block:before {
content: '';
position: absolute;
top: -50%;
left: -50%;
width: 200%;
height: 200%;
background: rgba(255, 255, 255, 0.1);
transform: rotate(45deg);
z-index: -1;
}

.block:after {
content: '';
position: absolute;
bottom: -50%;
right: -50%;
width: 200%;
height: 200%;
background: rgba(255, 255, 255, 0.1);
transform: rotate(45deg);
z-index: -1;
}
</style>