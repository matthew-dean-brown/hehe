<template lang="">
  <div>
    <!-- click event -->
    <button v-on:click="decrement()">Decrement</button>
    <h1>Counter -> <span>{{counter}}</span></h1>
    <!-- click event -->
    <button @click="increment()">Increment</button>
    <!-- Attach javascript value to an attribute tag -->
  </div>
  <br>
  
  <!-- attribute binding -->
  <img :src="imgUrl">
  <div>
    
    <!-- Class styling binding -->
    <h4 :class="{hello:check}">Conditional rendering</h4>
    <!-- conditional rendering -->
    <h1 v-if="check">The value is true</h1>
    <h1 v-else>The value is false</h1>
    <button @click="change()">Change state</button>
    
    <!-- conditional rendering -->
    <h1 v-show="check">This contains the v-show</h1>
    <ul>
      <!-- list rendering -->
      
      <!-- <li v-for="sport in sports" :key="sport">{{sport}}</li> -->
      <li v-for="({message},index) in objects" :key="index">{{message}}</li>
    </ul>
    <!-- one way data binding -->
    <h3>{{oneWayText}}</h3>
    <!-- two way data binding -->
    <h3>{{twoWayText}}</h3>
    <input type="text" v-model="twoWayText">
  </div>
  <!-- <info-comp first-name="hehe" last-name="    hehehehehe"/>
  <info-comp first-name="hehe1"/>
  <info-comp :object-data='singleObject'/> -->
  <info-comp>
    Hehe I am using slots
  </info-comp>
  <slot-comp>
      <template #slotTitle>
          <!-- Card Slot -->
      </template>
      <template #default>
          <!-- <img :src="imgUrl"> -->
      </template>
  </slot-comp>
</template>
<script>
/* eslint-disable */
import InfoComp from '../components/InfoComp.vue'
import SlotComp from '../components/SlotComp.vue'
export default {
  data(){
    return{
      counter: 0,
      imgUrl:'https://hatrabbits.com/wp-content/uploads/2017/01/random.jpg',
      check:true,
      sports:['soccer','netball','volleyball'],
      objects:[
        {message:'Hello There 1',id:1},
        {message:'Hello There 2',id:2},
        {message:'Hello There 3',id:3}
      ],
      singleObject:{
      name: 'Matthew',
      surname:'Brown'
    },
    oneWayText:'hehehehehe',
    twoWayText:'hehe2.0'
    }
    
  },
  components:{
    InfoComp,
    SlotComp
  },
  methods:{
    increment(){
      this.counter++
    },
    decrement(){
      this.counter--
    },
    change(){
      this.check = !this.check
    }
  }
}
</script>
<style scoped>
  h1{
    color:blue
  }
  .hello{
    color:orangered
  }
  img{
    width: 10rem
  }
</style>