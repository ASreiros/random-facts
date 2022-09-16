<template>
    <li>{{fact}}</li>
</template>

<script>
export default {
    name:"Fact",

    data(){
      return{
        fact: "",
        flag:1,
      }
    },

    async created () {
      
      this.fact =await this.get();

    },
    methods:{
    async refreshFacts(){
      console.log("clicked");
      this.facts =await this.get();
    },
    async get(){
    
        const res = await fetch(`https://asli-fun-fact-api.herokuapp.com`);
        const data = await res.json();
        this.flag = 0;
        return data.data.fact;
        }
    }
}
</script>

<style lang="scss" scoped>
    li{
        padding-top: 20px;
        color: darkgreen;
        text-shadow: 1px 0 0 #fff, 0 -1px 0 #fff, 0 1px 0 #fff, -1px 0 0 #fff;
        text-transform: uppercase;
    }
</style>