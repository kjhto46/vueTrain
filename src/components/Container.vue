<template>
  <div>
    컨테이너예요
    <Post v-for="(a,i) in instarData" :key="a" :instarData="instarData[i]" />
  </div>
</template>
<script>
import Post from './Post.vue'
export default {
  name : 'ContainerI',
  components : {
    Post,
  },
  props : {
    instarData : Object,
  }
}
</script>
<style>
  
</style>