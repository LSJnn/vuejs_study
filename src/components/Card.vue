<template>
<!-- 반복문 없이 가능. -> ? component는 반복 없애기 위한. -->
  <div>
    <img class=image :src="oneroom.image"/>
    <h4 @click="$emit('openModal')">{{oneroom.title}}</h4>
    <p>{{oneroom.price}} 원</p>
  </div>
</template>

<script>

export default {
  name: "Card",
  data() {
    return {
    }
  },
  props :{
  /*수정불가*/
    oneroom : Object,
  },
  methods:{

  }
}
</script>

<style scoped>
div{
  box-sizing: border-box;
}

.image{
  width: 100%;
  margin-top: 40px;
}
</style>