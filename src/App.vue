<template>
  <form @submit.prevent="creatPost">
    <label for="">firstname: </label>
    <input type="text" v-model="formData.firstname">
    <label for="">password: </label>
    <input type="text" v-model="formData.password">
    <input type="submit" value="subnit">
  </form>
  <Homes></Homes>
</template>
<script>
import Homes from './components/Home';
import axios from 'axios';
export default {
  components: {Homes},
  data (){
    return {
      fname: 'akib',
      formData: {
        firstname : '',
        password : ''
      }
    }
  },
  methods: {
    creatPost(){
      axios.post('https://jsonplaceholder.typicode.com/posts',this.formData).then(response => console.log(response)).then(error => console.log(error));
    }
  }
}
</script>
<style scoped>

</style>
