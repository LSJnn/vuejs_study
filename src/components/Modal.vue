<template>
  <div v-if="is_modal_open===true" class="black-bg">
    <div class="white-bg">
      <img class="image" :src="onerooms[item_i].image"/>
      <h4>{{onerooms[item_i].title}}</h4>
      <p>{{onerooms[item_i].content}}</p>
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