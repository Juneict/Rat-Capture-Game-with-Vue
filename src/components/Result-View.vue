<template>
    <div class="catched">
    </div>
    
    <p>Result is {{score}}</p>
    <div v-if="score<500">
      <p>Wow ! အရမ်းမြန်တာပဲ</p>  
    </div>
    <div v-else-if="score>500 && score<1000">
      <p>Nice ! မဆိုးဘူး မြန်ပါတယ်</p>  
    </div>
    <div v-else>
      <p>lol ! နှေးသေးတယ်</p>  
    </div>
</template>

<script>
export default {
    props:[
        "score"
    ]
}
</script>

<style scoped>
   .catched {
        width: 280px;
        height: 280px;
        margin: auto;
        background-image: url('https://st.depositphotos.com/2400497/4160/v/950/depositphotos_41604049-stock-illustration-vector-illustration-of-a-rat.jpg');
        background-size: cover;
        background-repeat: no-repeat;
    }
</style>