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
                    <article v-for="(card , index)  in cardsList" :key="cardsList.id" class="col-2 mb-3" :cardList="cardsList">
                        <div class="card w-100">
                            <img :src="card.card_images[0].image_url" class="card-img-top" alt="{{ card.name }}">
                            <div class="card-body bg-black text-white">
                                <p class="card-text text-info">{{card.name }}</p>
                                <p class="card-text text-warning">{{card.type }}</p>
                            </div>
                        </div>
                    </article>
                </div>
            </div>
        </div>
    
    </section>
</template>

<style lang="scss" scoped>
    p.text-warning {
        font-size: 10px;
    }
    p .text-info{
        font-size: 12px;
    }
</style>
