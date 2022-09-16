<template>
    <button @click="$emit('btn-clicked')">{{name}}</button>
</template>

<script>
    export default {
        name:"Refresh",
        props:{
            name:{
                type:String,
                default:"Refresh"
            }
        }
    }
</script>

<style lang="scss" scoped>
    button{
        padding: 10px 20px;
        background-color: lightgreen;
        border-radius: 15%;
        color: white;
        text-shadow: 1px 0 0 rgb(255, 0, 0), 0 -1px 0 rgb(255, 0, 0), 0 1px 0 rgb(255, 0, 0), -1px 0 0 rgb(255, 0, 0);
        text-transform: uppercase;
        font-size: 24px;
        cursor: pointer;

    }
</style>