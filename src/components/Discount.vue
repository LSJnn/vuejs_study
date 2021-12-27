<template>
  <div class="discount">
    <h3 >지금 결제하면 {{ discount }}% 할인</h3>
  </div>
</template>

<script>
export default {
  name: "Discount",
  data(){
    return{
      discount:30,
      mvisible:true,
    }
  },
  mounted(){
    var interval = setInterval(()=>this.discount-=1,1000);
    setTimeout(()=>clearInterval(interval),30000);
  }
};

</script>

<style>
.discount{
  background: antiquewhite;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
</style>