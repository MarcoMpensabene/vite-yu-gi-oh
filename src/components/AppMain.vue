<script >
import MainListCard from "./MainListCard.vue";
import MainSearch from "./MainSearch.vue";
import axios from "axios";
export default {
    components :{
        MainListCard,
        MainSearch,
    },
    data() {
        return {
            cardsList : [],
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
        }
    },
    created(){
        this.getCards();
    }
}
</script>

<template>
    <main >
        <!-- <MainSearch /> -->
        <MainListCard :cardsList="cardsList" />

    </main>
</template>

<style lang="scss" scoped>

</style>
