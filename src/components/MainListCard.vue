<script >
import MainSingleCard from "./MainSingleCard.vue"
export default {
    data() {
        return {
            
            }
        },
    components : {
        MainSingleCard ,
    },
    props : {
        cardsList : {
            type : Array ,
            required : true 
        }
    }
}
</script>

<template>
    <section class="cards-list container mt-3">
        <div class="row">
            <div class="col12 text-white bg-dark pt-2 text-center text-uppercase fw-bolder">
                <p>Found {{ cardsList.length }} Cards</p>
            </div>
            
            <div class="col-12">
                <div class="row bg-white">
                    <MainSingleCard v-for="(card , index)  in cardsList" :key="cardsList.id"  :cardsList="card" />
                </div>
            </div>
        </div>
    
    </section>
</template>

<style lang="scss" scoped>

</style>
