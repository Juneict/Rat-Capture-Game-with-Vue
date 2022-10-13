<template>
    <div class="block" v-if="showBlock" :class="{catched:mouseCatched==true}" @click="stopTimer">
    </div>
</template>

<script>
export default {
    data(){
       return{
            showBlock:false,
            score:0,
            timer:null,
            mouseCatched:false,
       } 
    },
    props:["delay"],
    mounted(){
        setTimeout(()=>{
            this.showBlock = true;
            this.startTimer()
        },this.delay)
    },
    methods:{
        startTimer(){
            this.timer = setInterval(() => {
                this.score+=50;
            }, 50);
        },
        stopTimer(){
            clearInterval(this.timer);
            this.mouseCatched = true;
            this.$emit('endGame',this.score);
        }
    }
}
</script>

<style>
    .block{
        width: 280px;
        height: 280px;
        margin: auto;
        background-image: url('https://cdn1.vectorstock.com/i/1000x1000/34/10/rat-with-a-cheese-vector-23193410.jpg');
        background-size: cover;
        background-repeat: no-repeat;
    }  
    .catched {
        width: 280px;
        height: 280px;
        margin: auto;
        background-image: url('https://st.depositphotos.com/2400497/4160/v/950/depositphotos_41604049-stock-illustration-vector-illustration-of-a-rat.jpg');
        background-size: cover;
        background-repeat: no-repeat;
    }
</style>