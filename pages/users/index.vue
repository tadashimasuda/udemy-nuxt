<template>
    <div>
        <h1>user page</h1>
        
        <input type="text" v-model="id">
        <button @click="loadUser">loadUser</button>
    </div>
</template>

<script>
export default {
    data(){
        return {
            id:''
        }
    },
    methods:{
        loadUser(){
            this.$router.push(`/users/${this.id}`)
        }
    }
}
</script>