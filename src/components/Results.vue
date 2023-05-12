<template>
    <h2>Reaction time: <span>{{score}}ms</span></h2>
    <p class="rank">{{rank}}</p>
</template>

<script>
export default {
props: ['score'],
data() {
    return {
        rank: null
    }
},
mounted() {
    if (this.score < 350) {
        this.rank = 'Ninja Fingers'
    } else if (this.score < 600) {
        this.rank = 'Rapid Reflexes'
    } else {
        this.rank = 'Snail pace...'
    }
} 
}
</script>

<style>
h2 {
    margin-top: 40px;
}

h2 span {
    color: rgb(168, 16, 16);
}
.rank {
    font-size: 1.4em;
    color: rgb(168, 16, 16);
    background-color: rgb(248, 239, 226);
    width: 300px;
    padding: 30px;
    font-weight: 600;
    border-radius: 50%;
    margin: 40px auto;
    border: 4px dashed rgb(168, 16, 16);;
}

</style>