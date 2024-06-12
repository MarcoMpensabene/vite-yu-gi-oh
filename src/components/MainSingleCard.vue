<script >
export default {
    data() {
        return {
            
            }
        },
    props :{
        cardsList : {
            type : Array,
            required : true
        }
    }
}
</script>

<template>
    <article class="col-2 mb-3">
    <div class="card w-100">
        <img :src="cardsList.card_images[0].image_url" class="card-img-top" alt="{{ cardsList.name }}">
            <div class="card-body bg-black text-white">
                <p class="card-text text-info">{{cardsList.name }}</p>
                <p class="card-text text-warning">{{cardsList.type }}</p>
            </div>
        </div>
    </article>
</template>

<style lang="scss" scoped>
    p.text-warning {
        font-size: 10px;
    }
    p .text-info{
        font-size: 12px;
    }

</style>
