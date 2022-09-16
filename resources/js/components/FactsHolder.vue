<template>
    <div class="facts-holder">
        <Refresh @btn-clicked="refreshFacts" name="Refresh facts"></Refresh>
        <ul v-for="index in 5" :key="index">
            <Fact></Fact>
        </ul>
    </div>
</template>

<script>
import Refresh from './Refresh.vue';
import Fact from './Fact.vue';
    export default {
    name: "FactsHolder",
    components: { Refresh, Fact },
    data(){
      return{
        facts:[]
      }
    },

    async created () {
      
      this.facts =await this.get();

    },
    methods:{
    async refreshFacts(){
      console.log("clicked");
      this.facts =await this.get();
    },
    async get(){
       let reply = [];

        for (let i = 0; i < 5; i++) {
            const res = await fetch(`https://asli-fun-fact-api.herokuapp.com`);
            const data = await res.json();
            reply.push(data.data.fact);
        }
        console.log(reply);
        return reply;
        }
    }
}


</script>

<style lang="scss" scoped>
    .facts-holder{
        margin-top: 20px;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;

        ul{
            width: 50vw;
            margin: 0 auto;
            text-align: left;

            li{
                padding-top: 20px;
                color: darkgreen;
                text-shadow: 1px 0 0 #fff, 0 -1px 0 #fff, 0 1px 0 #fff, -1px 0 0 #fff;
                text-transform: uppercase;
            }
        }
    }
</style>