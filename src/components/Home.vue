<template>
    <div>
        <app-carousel></app-carousel>
        <br>
        <br>
        <defiler :items="items"></defiler>
        <br>
        <br>
        <defiler :items="items"></defiler>
        <br>
        <br>
        <defiler :items="items"></defiler>
    </div>
</template>

<script>
import AppCarousel from './AppCarousel'
import Defiler from './Defiler'
export default {
    components: {AppCarousel, Defiler},
    
    data(){
        return {
            
        items: [
          {
            title: 'Obj1',
            name: 'Description',
            price: '107.45',
            link: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg'
          },
          {
            title: 'Obj1',
            name: 'Description',
            price: '107.45',
            link: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg'
          },
          {
            title: 'Obj1',
            name: 'Description',
            price: '107.45',
            link: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg'
          },
          {
            title: 'Obj1',
            name: 'Description',
            price: '107.45',
            link: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg'
          },
          {
            title: 'Obj1',
            name: 'Description',
            price: '107.45',
            link: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg'
          },
          {
            title: 'Obj1',
            name: 'Description',
            price: '107.45',
            link: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg'
          },
          {
            title: 'Obj1',
            name: 'Description',
            price: '107.45',
            link: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg'
          },
          {
            title: 'Obj1',
            name: 'Description',
            price: '107.45',
            link: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg'
          },
          {
            title: 'Obj1',
            name: 'Description',
            price: '107.45',
            link: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg'
          },
          {
            title: 'Obj1',
            name: 'Description',
            price: '107.45',
            link: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg'
          },
          {
            title: 'Obj1',
            name: 'Description',
            price: '107.45',
            link: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg'
          },
          {
            title: 'Obj1',
            name: 'Description',
            price: '107.45',
            link: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg'
          },
        ]
        }
    }
    
}
</script>

<style>

</style>
