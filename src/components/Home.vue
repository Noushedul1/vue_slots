<template>
    <div>
        <div v-for="post in posts" :key="post.id">
            <p>{{post.id}} {{post.title}}</p>
            <h3>{{post.body}}</h3>
            <hr/>
        </div>
        <button @click="getPosts()">{{fname}}</button>
    </div>
</template>
<script>
import axios from 'axios';
export default {
    data(){
        return{
            fname: 'get data',
            posts: []
        }
    },
    methods: {
        getPosts(){
            axios.get('https://jsonplaceholder.typicode.com/posts').then((response)=>{
                console.log(response.data);
                this.posts = response.data.slice(0,10);
            }).then((error)=>{
                console.log(error);
            });
        }
    }
}
</script>
<style scoped>

</style>
