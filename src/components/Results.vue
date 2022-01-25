<template>
  <p >Your Reaction Time:{{score}} ms</p>
  <p class="rank">{{rank}}</p>
</template>

<script>
import { onMounted } from 'vue'
export default {
props: ['score'],

data(){
return{rank:null}

},
mounted(){
if(this.score < 500){
    this.rank='Great!!!!!!!!!!'
}
else if(this.score<1000){
    this.rank="Fast Reflexes!!!!!"
}
else{
    this.rank = 'You can do better!'
}
}
}

</script>


<style>
.rank{font-size: 50px;
color: darkmagenta;
font-weight: bold;
}

</style>