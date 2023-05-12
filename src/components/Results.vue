<template>
    <h2>Reaction time: {{score}}ms</h2>
    <p>{{rank}}</p>
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

</style>