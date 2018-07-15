<template>
    <div>
        <article v-on:click="openPost"  >
            <div>
                <div  class="smallPost" :style="{backgroundImage: 'url('+this.l+');', backgroundColor:this.bgcolor}"></div>
            </div> 
        </article>
        <transition name="preview-action">
            <div v-if="!postsize">
                <postPreview :link="this.link" @close="openPost" ></postPreview>
            </div>
        </transition> 
    </div>
</template>

<script>
import PostPreview from "~/components/PostPreview.vue"
export default {
    props:["link","bgcolor"],
    components:{
        PostPreview
    },
    data:function(){
        return{
            post:'',
            postsize:true,
            l:this.link,
            
        }
    },
    mounted:
        function () {
            console.log(this.link)
        },
    methods:{
        openPost:function(){
            this.postsize=!this.postsize;
        }
    }
    
}
</script>

<style scoped>

.preview-action-active {
  animation: bounce-in .5s;
}
.preview-action-active {
  animation: bounce-in .5s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
.smallPost{
    height: 300px;
    background-position:center;
    background-repeat: no-repeat;
    width: 100%;
         -webkit-transition: all 0.5s ease;;
  -moz-transition: all 0.5s ease;;
  -o-transition: all 0.5s ease;;
  transition: all 0.5s ease;
}
.smallPost:hover{
   height:500px;
     -webkit-transition: all 0.5s ease;;
  -moz-transition: all 0.5s ease;;
  -o-transition: all 0.5s ease;;
  transition: all 0.5s ease;
  box-shadow: inset 0 0 0 10px #f190cc,inset 0 0 0 5px #ffffff;
}
</style>

