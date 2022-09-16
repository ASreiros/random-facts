<template>
    <div class="header">
        {{title}}
    </div>
</template>

<script>
    export default {
       name:"Header",
        props:{
            title:{
                type:String,
                default:"Default header"
            }
        }
    }
</script>

<style lang="scss" scoped>
    .header{
        width: 100%;
        display: flex;
        flex-direction: row;
        justify-content: center;
        font-size: 48px;
        text-shadow: 1px 0 0 rgb(255, 0, 0), 0 -1px 0 rgb(255, 0, 0), 0 1px 0 rgb(255, 0, 0), -1px 0 0 rgb(255, 0, 0);
        text-transform: uppercase;
    }
</style>