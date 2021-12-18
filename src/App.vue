<template>
  <Homes>
    <ul>
      <li v-for="foods in food" :key="foods">{{foods}}</li>
    </ul>
  </Homes>
</template>
 <script>
 import Homes from './components/Home';
 export default {
   components: {Homes},
   data() {
     return {
       food: ['banana','apple','Carrot']
     }
   }
 }
 </script>
 <style scoped>
 ul li{
   color: green;
 }
 </style>
 