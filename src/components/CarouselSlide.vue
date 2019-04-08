<template>
    <transition name="slide">
        <div class="box">            
            <div v-show="visible" class="boxItem">
                <img :src="it.link" width="100%" height="100px">
                <div class="descripBoxA">
                    <v-layout align-center row fill-height> <div  class="descripA">2D > Environments</div></v-layout>
                </div>
                <div class="info">
                    <div class="i1">SHMEL STUDIO</div>
                    <div class="i2">Platform Pack</div>
                    <div class="i3">(not enough ratings)</div>
                    <div class="i4">$5.36</div>
                </div>
            </div>
        </div> 
    </transition>   
</template>

<script>
export default {
    data(){
        return {
        }
    },

    computed:{
        visible (){
            return this.index >= this.$parent.index
        }
    },
    
    props: {
        it: {type: Object},        
        index: {type:Number, default:0}
    }
}
</script>

<style>
    .slide-enter-active{
        animation: slideIn .5s;
    }
    .slide-leave-active {
        animation: slideOut .5s;
        position: absolute;
        top: 0px;
        left: 0px;
    }

    @keyframes slideIn {
        from {
            transform: translateX(100%);
        }
        to {
            transform: translateX(0);
        }
    }

    @keyframes slideOut {
        from {
            transform: translateX(0);
        }
        to {
            transform: translateX(-100%);
        }
    }

    .box{
        width: 200px;
        height: 350px;
    }
    .boxItem{
        margin-left: 10px;
        margin-top: 60px;
        width: 195px;
        height: 230px;
        border-radius: 3px;
    }

    .boxItem:hover {
        box-shadow: 5px 5px 10px grey; 
    }

    .descripBoxA {
        width: 100%;
        height: 25px;
        background-color: rgba(189, 189, 189, 0.5);
    }
    .descripA{
        font-size: 15px;
        margin-left: 5px;
        color: rgb(121, 121, 121);
    }

    h1{
        color: rgb(121, 121, 121);
    }

    .info {
        margin-left: 15px;
        margin-top: 10px;
    }

    .i1 {
        color: rgb(121, 121, 121);
        font-size: 12px;
        margin-top: 5px;
    }
    .i2 {
        color: rgb(36, 36, 36);
        font-size: 15px;
        margin-top: 5px;
    }
    .i3 {
        color: rgb(121, 121, 121);
        font-size: 12px;
        margin-top: 5px;
    }
    .i4 {
        color: rgb(36, 36, 36);
        font-size: 15px;
        margin-top: 5px;
    }
</style>
