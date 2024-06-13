<script >
import MainListCard from "./MainListCard.vue";
import MainSearch from "./MainSearch.vue";
import MainLoader from "./MainLoader.vue";
import axios from "axios";
export default {
    components :{
        MainListCard,
        MainSearch,
        MainLoader,
    },
    data() {
        return {
            cardsList : [],
            IsLoaded : false,
            typeList : [] ,

            }
        },
    methods : {
        getCards(){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=24&offset=10000')
                .then( (response) => {
                    console.log(response.data.data);
                    this.cardsList = response.data.data;
                })
                .catch(function (error) {
                    console.log(error);
                })
                .finally(function () {
                });
        },
        getTypes(){
            axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
                .then( (response) => {
                    console.log(response.data);
                    this.typeList = response.data;
                })
                .catch(function (error) {
                    console.log(error);
                })
                .finally(function () {
                });
        },
        loadInSec(){
            setTimeout( ()=> {
                this.IsLoaded = true
                
            } , 5000);
        },
        cardsFilter(index){
            console.log(this.typeList[index].archetype_name)
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype='+ this.typeList[index].archetype_name)
                .then( (response) => {
                    console.log(response.data.data);
                    this.cardsList = response.data.data;
                })
                .catch(function (error) {
                    console.log(error);
                })
                .finally(function () {
                });
        },
    },
    created(){
        this.getCards();
        this.loadInSec();
        this.getTypes();
    }
}
</script>

<template>
    <main >
        <MainSearch :typeList="typeList" @chooseType="cardsFilter"/>
        <MainListCard :cardsList="cardsList" v-if="IsLoaded" />
        <MainLoader v-else />
    </main>
</template>

<style lang="scss" scoped>

</style>
