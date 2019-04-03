<template>
    <div>
        <slot></slot>
        <button class="carousel__nav carousel__next" @click.prevent="next">Suivant</button>
        <button class="carousel__nav carousel__prev" @click.prevent="prev">Precedent</button>
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

</style>
