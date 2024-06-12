<script >

export default {
    data() {
        return {
            
            }
        },
    }
</script>

<template>
    <div class="fs-1 d-flex justify-content-center text-danger">
        LOADING.................
    </div>
    <div class="card-wrapper">
        <img class="card" src="../assets/front.jpg" alt="" />
        <img class="card card-back" src="../assets/back.jpg" alt="" />
    </div>
</template>

<style lang="scss" scoped>
@keyframes cardFlip {
    0% {
    transform: rotateY(0deg);
    }
    50% {
    transform: rotateY(180deg);
    }
    100% {
    transform: rotateY(0deg);
    }
}

.card-wrapper {
    position: relative;
    transform-style: preserve-3d;
    animation: cardFlip 3s ease-in-out infinite;
    width: 100vw;
    height: 100vh;
}

.card {
    position: absolute;
    backface-visibility: hidden;
    width: 400px;
    height: 700px;
    margin-left: 500px;
    margin-top: 100px;
}

.card-back {
    transform: rotateY(180deg);
}
</style>
