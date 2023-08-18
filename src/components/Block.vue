<template>
    <div class="block" v-if="showBlock" @click="stopTimer">
        click me
    </div>
</template>

<script>
    export default {
        props: ['delay'],
        data(){
            return{
                showBlock: false,
                timer: null,
                reactionTime: 0
            }
        },
        mounted(){
            setTimeout(
                () => {
                    this.showBlock = true
                    this.startTimer()
                    //Above we are starting the timer to start immediately the block is mounted
                }, this.delay
            )
        },
        methods: {
            startTimer(){
                //This is the function to start the timer and our timer is running in ten milliseconds steps
                this.timer = setInterval(
                    () => {
                        this.reactionTime +=10
                    }, 10
                )
            },
            stopTimer(){
                clearInterval(this.timer)
                console.log(this.reactionTime)
            }
        }
    }
</script>

<style>
    .block{
        width: 400px;
        border-radius: 20px;
        background: #0faf87;
        color: white;
        padding: 100px 0;
        margin: 40px auto;
    }
</style>