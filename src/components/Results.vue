<template>
    <div>
        <p>Reaction time: {{ score }}ms</p>
        <p class="rank">{{ rank }}</p>
    </div>
</template>

<script>
    export default {
        props: ['score'],
        data(){
            return{
                rank: null
            }
        },
        mounted(){
            if (this.score < 100) {
                this.rank = "Superb Ninja Reflexes!!!"
            }else if (this.score < 250) {
                this.rank = "Ninja Reflexes!"
            }else if (this.score < 400) {
                this.rank = "Rapid Reflexes"
            } else {
                this.rank = "snail pace..."
            }
        }
    }
</script>

<style>
    .rank{
        font-size: 1.4em;
        color: #0faf87;
        font-weight: bold;
    }
</style>