<template>
    <div class="post">
        <div class="arrowToBack" v-on:click="close"></div>
        <div class="bigpost" :style="{backgroundImage: 'url('+this.link+');'}"></div>
    </div>
</template>
<script>
export default {
    props:["link"],
    methods:{
        close:function(){
            this.$emit('close')
        }
    }
}
</script>

<style scoped>
.arrowToBack{
    background-image: url('/arrow.png');
    background-size:cover;

    position:fixed;
    top:20px;
    left:40px;
    
    width: 64px;
    height: 64px;
    -webkit-transition: all 0.5s ease;;
    -moz-transition: all 0.5s ease;;
    -o-transition: all 0.5s ease;;
    transition: all 0.5s ease;
}
.bigpost{
    background-color:rgba(0, 0, 0, 0.00) !important;
    -webkit-transition: all 0.5s ease;;
    -moz-transition: all 0.5s ease;;
    -o-transition: all 0.5s ease;;
    transition: all 0.5s ease;
    height:100%;
    width:100%;

    background-position:center;
    background-repeat: no-repeat;
    background-size: contain;

}
.post{
    z-index: 10000;
    position: fixed;
    top:0px;left:0px;
    padding: 10px;
    width: 100%;
    height: 100%; 
    background-repeat: repeat;
    background-image: url('/bigPostBG.gif');
    background: rgba(0, 0, 0, 0.95);
    -webkit-transition: all 0.5s ease;;
    -moz-transition: all 0.5s ease;;
    -o-transition: all 0.5s ease;;
    transition: all 0.5s ease;
}
</style>

