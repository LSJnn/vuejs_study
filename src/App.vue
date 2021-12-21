<template>
  <div v-if="is_modal_open" class="black-bg">
    <div class="white-bg">
      <h4>상품 상세내용</h4>
      <p>상품 상세내용이ㅂ니다.</p>
      <button @click="clickReverse">닫기</button>
    </div>
  </div>

  <img alt="Vue logo" src="./assets/logo.png">

  <div class="menu">
    <a  v-for="menu in menus" :key="menu">
    {{menu}}
    </a>
  </div>

<!--  <div>
    <div v-for="(product,i) in products" :key = i>

      <h3>{{product}}</h3>
      <p>{{price[i]}}</p>
    </div>
  </div>-->
  <div>
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
  </div>
</template>

<script>
import onerooms from './assets/onerooom'

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
    }
  },
  methods : {
    clickBTN(){
      this.is_modal_open=true;
    },
    clickReverse(){
      this.is_modal_open=!this.is_modal_open;
    }
  },
  components: {
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

.image{
  width: 100%;
  margin-top: 40px;
}

</style>
