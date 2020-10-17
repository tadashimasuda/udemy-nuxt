<template>
    <div>
        <div>
            <h2>Making API request - the Vue way</h2>
            <hr>
        </div>
        <div class="container row">
            <Card v-for="post in posts" :key="post.id" :post ="post" class="ml-auto mr-auto"/>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
import Card from '@/components/Card'

export default {
     components :{
        Card
    },
    data(){
        return{
            posts:''
        }
    },
    async asyncData(){
        let {data} = await axios.get('https://jsonplaceholder.typicode.com/posts')
        return {posts:data}
    },
}
</script>