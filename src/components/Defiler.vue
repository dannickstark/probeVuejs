<template>
    <div>
        <carousel>
            <carouselSlide v-for="(item,i) in itemsSecond" :it="item" :key="i" :index="i"></carouselSlide>
        </carousel>
    </div>
</template>

<script>
import Carousel from './Carousel'
import CarouselSlide from './CarouselSlide'
export default {
    components: {CarouselSlide, Carousel},
    data (){
        return {
            itemsSecond: []
        }
    },

    props:{
        items:{type:Array}
    },

    mounted (){
        this.itemsSecond = this.items
    }
    
}
</script>

<style>

</style>
