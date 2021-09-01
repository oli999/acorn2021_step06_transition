<template>
  <div id="app">
      <h1>Vue transition 테스트12</h1>
      <input type="text" v-model="inputMsg">
      <button @click="add">추가</button>
      <button @click="remove">삭제</button>
      <button @click="shuffle">섞기</button>
      <transition-group tag="ul" 
        enter-active-class="animate__animated animate__slideInLeft"
        leave-active-class="animate__animated animate__slideOutRight">
          <li v-for="(tmp,index) in msgs" :key="index">{{tmp}}</li>
      </transition-group>
  </div>
</template>


<script>

import _ from 'lodash'

export default {
  name: 'App12',
  created(){
      console.log(_);
  },
  data(){
    return {
        msgs:["하나","두울"],
        inputMsg:""
    };
  },
  methods:{
   add(){
       //입력한 문자열을 배열에 추가 한다.
       this.msgs.push(this.inputMsg);
   },
   remove(){
       //제일 마지막 인덱스의 아이템 삭제 
       this.msgs.splice(this.msgs.length-1);
   },
   shuffle(){
       this.msgs = _.shuffle(this.msgs);
   }
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

</style>
