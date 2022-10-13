<template>
 <h1>ကြွက်ဖမ်းဂိမ်း</h1>
 <button @click="start" :disabled="isPlaying">ဖမ်းမယ်</button>
 <div v-if="isPlaying">
  <Block :delay="delay" :end="end" @endGame="endGame"></Block>
 </div>
 <div v-if="end">
  <Result :score="score"></Result>
 </div>

</template>

<script>
import Block from './components/BLock.vue'
import Result from './components/Result-View.vue'
export default {
  name: 'App',
  components: {
    Block ,Result
},
data(){
  return{
    isPlaying : false,
    delay :null,
    score:0,
    end:false,
    mouseCatched:null
  }
},
  methods:{
    start(){
      this.isPlaying = true;
      this.end = false;
      this.delay = 2000+Math.random()*5000
    },
    endGame(score){
      this.score = score;
      this.isPlaying = false;
      this.end =true
     
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
