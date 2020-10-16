<template>
    <div>
        <div>
            <h2>Making API request - the Vue way</h2>
            <hr>
        </div>
        <div class="container">
            <h4 v-for="post in posts" :key="post.id">{{post.title}}</h4>
        </div>
    </div>
</template>

<script>
import axios from 'axios'

export default {
    data(){
        return{
            posts:''
        }
    },
    async asyncData(){
        let {data} = await axios.get('https://jsonplaceholder.typicode.com/todos')
        return {posts:data}
    },
}
// import axios from 'axios'

// export default {
//     data(){
//         return{
//             posts:[]
//         }
//     },
//     mounted(){
//         axios.get('https://jsonplaceholder.typicode.com/todos')
//         .then(response => {
//             console.log(response.data)
//             this.posts = response.data
//         })
//         .catch(error => {
//             console.log(error)
//         }) 

//     }
// }
</script>