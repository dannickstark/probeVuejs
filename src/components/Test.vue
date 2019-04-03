<template>
    <div>
        <carousel>
            <carouselSlide>
                Salut les gens
                
            </carouselSlide>
            <carouselSlide>
                Aurevoir les gens
            </carouselSlide>
        </carousel>
        <todos></todos>
    </div>
</template>

<script>
import Todos from './Todos'
import Carousel from './Carousel'
import CarouselSlide from './CarouselSlide'
export default {
    components: {Todos,Carousel, CarouselSlide}
    
}
</script>

<style>

</style>
