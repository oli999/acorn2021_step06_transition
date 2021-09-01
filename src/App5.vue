<template>
  <div id="app">
      <h1>Vue transition 테스트5</h1>
      <input type="checkbox" v-model="isMake">
      <transition name="gura">
        <div v-if="isMake" class="box"></div>
      </transition> 
  </div>
</template>


<script>

export default {
  name: 'App5',
  data(){
    return {
      isMake:false
    };
  },
  methods:{
   
  }
}
</script>

<style scoped>
    /* 외부 css 로딩하기 */
    @import url(https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css);
</style>
<style>

  .box{
    width: 100px;
    height: 100px;
    border: 1px solid red;
    background-color: yellow;
  }

  .gura-enter-active{
      animation: bounceInDown 0.5s ease-out;
  }

  .gura-leave-active{
      animation: bounceOutRight 0.5s ease-out;
  }

</style>
