<template>
  <div id="app">
      <h1>Vue transition 테스트4</h1>
      <input type="checkbox" v-model="isMake">
      <transition name="gura">
        <div v-if="isMake" class="box"></div>
      </transition> 
  </div>
</template>

<script>

export default {
  name: 'App4',
  data(){
    return {
      isMake:false
    };
  },
  methods:{
   
  }
}
</script>

<style>

  .box{
    width: 100px;
    height: 100px;
    border: 1px solid red;
    background-color: yellow;
  }

  .gura-enter-active{
      animation: myAni 0.5s ease-out;
  }

  @keyframes myAni {
      0%{
          transform: translateY(-500px);
      }
      80%{
          transform: translateY(10px);
      }
      100%{
          transform: translateY(0px);
      }
  }

  .gura-leave-active{
      /* animation: yourAni 0.5s linear; */
      animation: myAni 0.5s reverse;
  }

  @keyframes yourAni{
      0%{
          opacity: 1.0;
      }
      100%{
          opacity: 0.0;
      }
  }

</style>
