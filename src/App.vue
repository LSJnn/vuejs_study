<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <h3>xx원룸</h3>
    <p>{{price1}}</p>
  </div>
  <div>
    <h3>yy원룸</h3>
    <p>{{price2}}</p>
  </div>

</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      price1 : 60,
      price2 : 70,
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
</style>
