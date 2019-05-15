<template>
<div>
    <h2>Welcome to Punch bag Game</h2>
    <!--<div id="bag" v-bind:class="{burst:ended}">-->
<div id="bag" v-bind:class="{ burst: ended }">
    </div>

    <!--<div id="bag-health">
      <div v-bind:style="{width:health+'%'}">

      </div>
    </div>-->
              <div id="bag-health">
                <div v-bind:style="{ width: health + '%' }"></div>
            </div>


    <div id="controls">
      <br>
      <button @click="punch">Punch</button>
      <button @click="restart">Restart</button>
    </div>

</div>
</template>

<script>
export default {
data(){
    return{
        health:100,
        ended:false
    }
},
methods:{
    punch(){
        this.health-=10;
        if(this.health==0){
            this.ended=true
        }
    },
    restart(){
        this.health=100
        this.ended=false
    }
}
}
</script>

<style scoped>
 p{
    color: red
}
#bag{
        width: 200px;
        height: 500px;
        margin: o auto;
        background: url(/src/assets/bag.png) center no-repeat;
        background-size: 80%;
  }
/*#bag .burst{
      width: 200px;
        height: 500px;
        margin: o auto;
   background: url(/src/assets/bag-burst.png) center no-repeat;
       
        background-size: 80%;
       
  }*/


#bag.burst{
    background-image: url(/src/assets/bag-burst.png);
      background-size: 80%;
}
 #bag-health{
     width: 200px;
     border: 2px solid black;
 }
 #bag-health div{
     height: 20px;
     background-color: red;
 }
</style>
