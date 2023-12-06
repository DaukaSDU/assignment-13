<template>
<div class="carousel">
    <div class="left" @click="curr_i = (curr_i == 1) ? length : (curr_i - 1)"></div>
    <div class="right" @click="curr_i = (curr_i == length) ? 1 : (curr_i + 1)"></div>
    <div class="carousel__container">
        <div class="carousel__item" v-for="item in items">
            <span v-if="item.i == curr_i">{{ item.alt }}</span>
            <img v-if="item.i == curr_i" :src="item.src" :alt="item.alt">
        </div>
    </div>
    <div class="carousel__path">
        <div v-for="i in length">
            <div v-if="i == curr_i" class="active"></div>
            <div v-else></div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    props: {
        items: Object
    },
    data() {
        return {
            length: this.items.length,
            curr_i: 1
        }
    }
}
</script>

<style>
* {
    transition: all .5s ease;
}

.carousel {
    padding-top: 10px;
    background-color: rgb(255, 174, 67);
    border-radius: 10px;
    width: 700px;
}

.carousel__container {
    display: flex;
    justify-content: center;
}

.carousel__item {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #fff;
    border-radius: 10px;
    height: 500px;
    text-align: center;
}

.carousel__item>img {
    border-radius: 10px;
    max-height: 480px;
}

.carousel__path {
    height: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
}

.carousel__path>div>div {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background-color: #ffffff76;
}

.carousel__path>div>div.active {
    background-color: #fff;
}

.left, .right {
    border-top: 30px solid transparent;
    border-bottom: 30px solid transparent;
    position: relative;
    top: 50%;
    transform: translateY(-50%);
    cursor: pointer;
    opacity: .7;
    margin: 0 5px;
}

.left {
    float: left;
    border-right: 30px solid #fff; 
}

.right {
    float: right;
    border-left: 30px solid #fff; 
}

.left:hover, .right:hover {
    opacity: 1;
}
</style>