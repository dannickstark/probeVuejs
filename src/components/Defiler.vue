<template>
    <div class="defiler">
        <h1>New release</h1>
        <br>
        <carousel>
            <v-layout align-center justify-start row fill-height>
                <carouselSlide v-for="(item,i) in itemsSecond" :it="item" :key="i" :index="i"></carouselSlide>
            </v-layout>
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
        items: {type:Array}
    },

    mounted (){
        this.itemsSecond = this.items
    }
    
}
</script>

<style>
.defiler {
    vertical-align: middle;
}
</style>
