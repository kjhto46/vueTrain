<template>
  <div :class="`filter-item ${imgFilter}`" :style="`background:url(${이미지}) center/cover`">
  <slot name="a"></slot>.
  <slot name="b"></slot>
  <button @click="fire">버튼</button>
  </div>
</template>
<script>
export default {
  name: "filterBox",
  props:{
    imgFilter:String,
    이미지:String,
  },
  methods:{
    fire(){
      this.emitter.emit('fireFilterName', this.imgFilter)
    }
  }
};
</script>
<style>
.filter-item {
  width: 100px;
  height: 100px;
  margin: 10px 10px 10px auto;
  padding: 8px;
  display: inline-block;
  color: white;
  background-size: cover;
  background-position: center;
}
</style>
