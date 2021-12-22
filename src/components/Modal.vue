<template>
  <div v-if="is_modal_open===true" class="black-bg">
    <div class="white-bg">
      <img class="image" :src="onerooms[item_i].image"/>
      <h4>{{onerooms[item_i].title}}</h4>
      <p>{{onerooms[item_i].content}}</p>
      <p><input v-model="month" /></p>
      <!--      <p><input type="number" v-model="month" /></p>-->
<!--      <p><input type="number" min="1" max="12" step="1" v-model="month" /></p>-->
      <p>사용자가 {{month}} 개월을 선택함</p>
      <p>{{month*onerooms[item_i].price}} 원</p>
     <button @click="$emit('modalClose')">닫기</button>
    </div>
  </div>
</template>

<script>

export default {
  name: "Modal",
  props: {
    /*props 이름 : 데이터 형식*/
    onerooms : Array,
    item_i : Number,
    is_modal_open: Boolean,
  },
  data(){
    return {
      month:1,
    }
  },
  watch :{
    /*month 변수의 데이터 변할때마다 watcher 실행됨.*/
    month(a){
      if(a>13){
        alert('13초과 입력 불가');
        a=1;
        this.month=1;
      }
      if(isNaN(a)==true){
        alert('숫자만 입력해주세요');
        a=1;
        this.month=1;
      }
    }
  },
  methods :{
  }

}

</script>

<style>
.black-bg{
  width: 100%; height: 100%;
  position: fixed; padding: 20px;
  background: rgba(0,0,0,0.5);

}
.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
.image{
  width: 100%;
}

</style>