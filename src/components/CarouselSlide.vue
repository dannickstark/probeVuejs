<template>
    <div v-show="visible">
        <img :src="it.link" width="200px" height="200px">
    </div>    
</template>

<script>
export default {
    data(){
        return {
        }
    },

    computed:{
        visible (){
            return this.index === this.$parent.index
        }
    },
    
    props: {
        it: {type: Object},        
        index: {type:Number, default:0}
    }
}
</script>

<style>

</style>
