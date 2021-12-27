<template>
<!-- 클래스명 넣을 때 object 형식으로 넣음 = trye 일떄만. -->
<!--  <div class="start" :class="{end : is_modal_open==true}">-->
<transition name="fade">
    <Modal @modalClose="is_modal_open=false" :onerooms = "onerooms" :is_modal_open="is_modal_open" :item_i="item_i">
    <!-- 데이터 하드코딩 입력 가능
        변수명 ="문자"
        :변수명 = 숫자
        :변수명 = "리스트.속성" :변수명2="리스트.속성2" 는 V-bind="리스트변수 이름" (리스트내 각각 할당)
        -->
    </Modal>
</transition>
<!--  </div>-->
  <img alt="Vue logo" src="./assets/logo.png">

  <div class="menu">
    <a  v-for="menu in menus" :key="menu">
    {{menu}}
    </a>
  </div>

  <discount v-if="showDiscount == true"/>
  <!--  <div v-for="(oneroom,i) in onerooms" :key="i">
      <Card :oneroom="onerooms[i]"/>
    </div>-->
  <button @click="priceSort">가격순정렬</button>
  <button @click="priceSort_re">가격순 역정렬</button>
  <button @click="priceSort_name">이름순 정렬</button>
  <button @click="priceSort_back">되돌리기</button>
  <button @click="priceSort_filter">필터</button>
  <Card @openModal="is_modal_open=true" :item_i="i" :oneroom="array[i]" v-for="(oneroom,i) in array" :key="i"/>>
<!--  <di>
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
      showDiscount:true,
      price1 : 60,
      price2 : 70,
      menus : ["Home", "Shop", "About"],
      products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
      array:onerooms,
      onerooms: onerooms,
      o_onerooms:[...onerooms],
      price : [40,60,30],
      click_cnt: [0,0,0],
      is_modal_open:false,
      item_i:0,
    }
  },
  methods : {
    priceSort(){
      this.onerooms.sort(function (a,b){
        return a.price - b.price;
      });
      this.array=this.onerooms;
    },
    priceSort_re() {
      this.onerooms.sort(function (a, b) {
        return b.price - a.price;
      });
      this.array=this.onerooms;
    },
    priceSort_name() {
      this.onerooms.sort(function(a,b){
        return a.title.localeCompare((b.title));
      });
      this.array=this.onerooms;
    },
    priceSort_back() {
      return this.array=this.o_onerooms;
    },
    priceSort_filter(){
      var newarr = new Array();
      for(var i of this.array){
        if(i.price>500000){
          newarr.push(i);
        }
        this.array=newarr;
      }
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
/*입장 시*/
.fade-enter-from{
  /*시작 스타일*/
  transform: translateY(-1000px);
}
.fade-enter-active{
  transition: all 1s;
}
.fade-enter-to{
  /*끝 스타일*/
  transform: translateY(0px);
}
/*퇴장 시*/
.fade-leave-from{
  opacity: 1;
}
.fade-leave-active{
  transition: all 1s;
}
.fade-leave-to{
  opacity:0;
}

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
.start{
  opacity: 0;
  /*모든 속성이 변할 떄 1초에 걸쳐 변경*/
  transition: all 1s;
}
.end{
  opacity: 1;
}
</style>
