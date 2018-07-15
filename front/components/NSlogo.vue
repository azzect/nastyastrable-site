<template>
    <div>
        <div>
            <h1 class="logo" @click="moveMenu">nastyastrable</h1>
        </div>
        <transition name="menu-move">
            <div v-if="menu" class="menu">
                <nav>
                    <div class="row"><button>/home</button></div>
                    <div class="row"><button>/projects</button></div>
                    <div class="row"><button>/contacts</button></div>
                    <div class="row"><button>dev by</button></div>
                </nav>
            </div>
        </transition>
    </div>
</template>

<script>
export default {
    data:function(){
        return{
            menu:false
        }
    },
    methods:{
        moveMenu:function(){
            this.menu=!this.menu;
            console.log('menu is'+ this.menu)
        }
    }
}
</script>


<style scoped>
@import url('https://fonts.googleapis.com/css?family=Encode+Sans+Condensed:900');
@import url('https://fonts.googleapis.com/css?family=Roboto');
@import url('https://fonts.googleapis.com/css?family=Markazi+Text');

div{
    font-family: 'Markazi Text', serif;
}
.menu-move-active, .menu-move-leave-active {
  transition: opacity .5s;
}
.menu-move-enter, .menu-move-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
.logo{
    z-index:100;
    position: fixed;
    top: 20px;
    left: 40px;
    color: #ffffff;
    font-family: 'Markazi Text', serif;
    text-shadow: 4px 4px 4px #f190cc;
    
}
.menu{
    z-index:90;
    position: fixed;
    left:0px;
    top:0px;
    height: 100%;
    width: 400px;
    background-image: url('/bigPostBG.gif')!important;
    background-repeat: repeat;
    background: rgba(0, 0, 0, 0.95);
    -webkit-transition: all 0.5s ease;;
    -moz-transition: all 0.5s ease;;
    -o-transition: all 0.5s ease;;
    transition: all 0.5s ease;

    padding-top:100px;
}
.row{
    margin-left: 35px;
    padding: 5px;
}
</style>
