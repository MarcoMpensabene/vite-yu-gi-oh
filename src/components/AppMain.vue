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
            IsLoaded : false
            }
        },
    methods : {
        getCards(){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=24&offset=1000')
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
        loadInSec(){
            setTimeout( ()=> {
                this.IsLoaded = true
                
            } , 5000);
        }
    },
    created(){
        this.getCards();
        this.loadInSec();
    }
}
</script>

<template>
    <main >
        <!-- <MainSearch /> -->
        <MainListCard :cardsList="cardsList" v-if="IsLoaded" />
        <MainLoader v-else />
    </main>
</template>

<style lang="scss" scoped>

</style>
