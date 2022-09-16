<template>
    <div class="facts-holder">
        <Refresh @btn-clicked="deleteFacts" name="Refresh facts"></Refresh>
        <ul v-for="index in facts" :key="index">
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
        facts:5,
      }
    },

    async created () {
      
      this.facts =await this.get();

    },
    methods:{
    deleteFacts(){
        this.facts = 0;
        setTimeout(this.refreshFacts, 1)
    },    
    refreshFacts(){
      console.log("clicked");
      this.facts = 5;
    },
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