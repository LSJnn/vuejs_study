<template>

<Modal @modalClose="is_modal_open=false" :onerooms = "onerooms" :is_modal_open="is_modal_open" :item_i="item_i">
<!-- 데이터 하드코딩 입력 가능
    변수명 ="문자"
    :변수명 = 숫자
    :변수명 = "리스트.속성" :변수명2="리스트.속성2" 는 V-bind="리스트변수 이름" (리스트내 각각 할당)
    -->
</Modal>

  <img alt="Vue logo" src="./assets/logo.png">

  <div class="menu">
    <a  v-for="menu in menus" :key="menu">
    {{menu}}
    </a>
  </div>

<discount/>
<!--  <div v-for="(oneroom,i) in onerooms" :key="i">
    <Card :oneroom="onerooms[i]"/>
  </div>-->

  <Card @openModal="is_modal_open=true; item_i=i" :oneroom="onerooms[i]" v-for="i in onerooms.length-1" :key="i"/>
<!--  <div>
    <img class=image src="./assets/images/room0.jpg">
    <h3>{{onerooms[0].title}}</h3>
    <p>{{onerooms[0].price}}</p>
    <button @click="clickBTN">허위매물 신고 버튼</button>
  </div>
  <div>
    <img class=image src="./assets/images/room1.jpg">
    <h3>{{onerooms[1].title}}</h3>
    <p>{{onerooms[1].price}}</p>
    <button @click="clickBTN">허위매물 신고 버튼</button>
  </div>
  <div>
    <img class=image src="./assets/images/room2.jpg">
    <h3>{{onerooms[0].title}}</h3>
    <p>{{onerooms[2].price}}</p>
    <button>허위매물 신고 버튼</button>
  </div>-->

</template>

<script>
import onerooms from './assets/onerooom'
import Discount from "@/components/Discount";
import Modal from "@/components/Modal";
import Card from "@/components/Card";

export default {
  name: 'App',
  data(){
    return{
      price1 : 60,
      price2 : 70,
      menus : ["Home", "Shop", "About"],
      products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
      onerooms: onerooms,
      price : [40,60,30],
      click_cnt: [0,0,0],
      is_modal_open:false,
      item_i:0,
    }
  },
  components: {
    Modal : Modal,
    Discount : Discount,
    Card : Card,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
}
body{
  margin: 0;
}
div{
  box-sizing: border-box;
}

.menu {
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  font-family: "Bell MT";
  color: white;
  padding: 20px;
  font-size: 20px;
}
</style>
