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
            <div class="col12 text-white bg-dark ">
                <p>Found {{ cardsList.length }} Cards</p>
            </div>
            
            <div class="col-12">
                <div class="row bg-white">
                    <article v-for="card  in cardsList" :key="card.id" class="col-2">
                        <div class="card w-100" v-for="image in card.card_images">
                            <img :src="image.image_url" class="card-img-top" alt="{{ card.name }}">
                            <div class="card-body bg-black text-white">
                                <p class="card-text ">{{card.name }}</p>
                                <p class="card-text ">{{card.type }}</p>
                            </div>
                        </div>
                    </article>
                </div>

                <MainSingleCard />
            </div>
        </div>
        <MainSingleCard />
    </section>
</template>

<style lang="scss" scoped>
    p.card-text{
        font-size: 10px;
    }

</style>
