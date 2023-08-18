<template>
    <div class="block" v-if="showBlock">
        click me
    </div>
</template>

<script>
    export default {
        props: ['delay'],
        data(){
            return{
                showBlock: false
            }
        },
        mounted(){
            console.log("component mounted")
            setTimeout(
                () => {
                    this.showBlock = true
                    console.log(this.delay)
                }, this.delay
            )
        },
        updated(){
            console.log("component updated")
        }
        //The mounted() and updated() are the examples of lifecycle hooks
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