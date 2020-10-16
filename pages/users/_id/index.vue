<template>
    <h1>users_id{{$route.params.id}}</h1>
</template>
<script>
export default {
    validate(context){
        return /^\d+$/.test(context.params.id);
    }
}
</script>