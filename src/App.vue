<template>
    <h1>Tony Reaction Timer</h1>
    <button @click="start" :disabled="isplaying">play</button>
    <!--We are now setting the emitted value to a function using '@end="endGame"'-->
    <Block v-if="isplaying" :delay="delay" @end="endGame"/>
    <p v-if="showResults">Reaction time: {{ score }}ms</p>
</template>


<script>
    import Block from "./components/Block.vue"

    export default{
        name: 'App',
        components: { Block },
        data(){
            return{
                isplaying: false,
                delay: null,
                score: null,
                showResults: false
            }
        },
        methods: {
            start() {
                this.isplaying = true
                this.delay = 2000 + Math.random() * 5000
                //hiding the results
                this.showResults = false
            },
            endGame(reactionTime) {
                //setting the score property to the reaction time emitted from the child component
                this.score = reactionTime
                //Setting the game status to ended
                this.isplaying = false
                //Making The Results to show
                this.showResults = true
            }
        }
    }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #444;
        margin-top: 60px;
    }
</style>
