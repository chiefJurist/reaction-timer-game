<template>
    <h1>Tony Reaction Timer</h1>
    <button @click="start" :disabled="isplaying">play</button>
    <!--Above we are setting the play button to be disabled while we play-->
    <!--Below we set the delay for the block appearance-->
    <Block v-if="isplaying" :delay="delay"/>
</template>


<script>
    import Block from "./components/Block.vue"

    export default{
        name: 'App',
        components: { Block },
        data(){
            return{
                isplaying: false,
                delay: null
            }
        },
        methods: {
            start() {
                this.isplaying = true
                this.delay = 2000 + Math.random() * 5000
                console.log(this.delay)
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
