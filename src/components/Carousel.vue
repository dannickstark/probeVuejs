<template>
        <div class="carousel">
            <slot></slot>
            <button class="carousel__nav carousel__next" @click.prevent="next"></button>
            <button class="carousel__nav carousel__prev" @click.prevent="prev"></button>
        </div>
</template>

<script>
export default {
    data (){
        return {
            index: 0,
            slides: []
        }
    },

    mounted () {
        this.slides = this.$children
    },

    methods:{
        next (){
            this.index ++
            if(this.index >= this.slidesCount){
                this.index = 0
            }
        },
        prev (){
            this.index --
            if(this.index < 0){
                this.index = this.slidesCount - 1
            }
        }
    },

    computed: {
        slidesCount () { return this.slides.length }
    }
    
}
</script>

<style>
.carousel {
    position: relative;
    width: 80%;
    height: 250px;
    overflow-x: hidden;
    overflow-y: hidden;
}

.carousel__nav{
    position: absolute;
    top: 50%;
    margin-top: -25px;
    left: 10px;
    background: url(../assets/prev.png);
    width: 50px;
    height: 50px ;
}

.carousel__nav.carousel__next{
    right: 10px;
    left: auto;
    background: url(../assets/next.png);
}
</style>
