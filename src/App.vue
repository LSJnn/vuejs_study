<template>
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
      <button>허위매물 신고 버튼 : {{cnt}}</button>
    </div>
  </div>-->

  <div>
    <h3>{{product[0]}}</h3>
    <p>{{price[0]}}</p>
    <button>허위매물 신고 버튼</button>
  </div>
  <div>
    <h3>{{product[1]}}</h3>
    <p>{{price[1]}}</p>
    <button>허위매물 신고 버튼</button>
  </div>
  <div>
    <h3>{{product[2]}}</h3>
    <p>{{price[2]}}</p>
    <button>허위매물 신고 버튼</button>
  </div>

</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      price1 : 60,
      price2 : 70,
      menus : ["Home", "Shop", "About"],
      products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸'],
      price : [40,60,30],
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
  margin-top: 60px;
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
