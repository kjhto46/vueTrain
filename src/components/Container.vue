<template>
  <div>
    <div v-if="step == 0">
      <Post v-for="(a, i) in instarData" :key="a" :instarData="instarData[i]" />
    </div>

    <div v-if="step == 1">
      <!-- 필터선택페이지 -->
      <div
      :class="선택한필터"
        class="upload-image"
        :style="{ backgroundImage: `url(${이미지})` }"
      ></div>
      <div class="filters">
        <FilterBox v-for="(필터, i) in imgFilter" :key="필터" :imgFilter="imgFilter[i]" :이미지="이미지">
          <template v-slot:a> {{ i }}</template>
          <template v-slot:b> {{필터}}</template>
        </FilterBox>
      </div>
    </div>

    <div v-if="step == 2">
      <!-- 글작성페이지 -->
      <div
      :class="선택한필터"
        class="upload-image"
        :style="{ backgroundImage: `url(${이미지})` }"
      ></div>
      <div class="write">
        <textarea @input="wrtieTxt" class="write-box">write!</textarea>
      </div>
    </div>
  </div>
</template>
<script>
import Post from "./Post.vue";
import FilterBox from "./FilterBox.vue";
export default {
  name: "ContainerI",
  data() {
    return {
      imgFilter: [
        "aden",
        "_1977",
        "brannan",
        "brooklyn",
        "clarendon",
        "earlybird",
        "gingham",
        "hudson",
        "inkwell",
        "kelvin",
        "lark",
        "lofi",
        "maven",
        "mayfair",
        "moon",
        "nashville",
        "perpetua",
        "reyes",
        "rise",
        "slumber",
        "stinson",
        "toaster",
        "valencia",
        "walden",
        "willow",
        "xpro2",
      ],
    };
  },
  components: {
    Post,
    FilterBox,
  },
  props: {
    instarData: Object,
    step: Number,
    이미지: String,
    선택한필터: String,
  },
  methods: {
    wrtieTxt(event) {
      this.$emit("writeTxt", event.target.value);
    },
  },
};
</script>
<style>
.upload-image {
  width: 100%;
  height: 450px;
  background: cornflowerblue;
  background-size: cover;
}
.filters {
  overflow-x: scroll;
  white-space: nowrap;
}
.filter-1 {
  width: 100px;
  height: 100px;
  background-color: cornflowerblue;
  margin: 10px 10px 10px auto;
  padding: 8px;
  display: inline-block;
  color: white;
  background-size: cover;
}
.filters::-webkit-scrollbar {
  height: 5px;
}
.filters::-webkit-scrollbar-track {
  background: #f1f1f1;
}
.filters::-webkit-scrollbar-thumb {
  background: #888;
  border-radius: 5px;
}
.filters::-webkit-scrollbar-thumb:hover {
  background: #555;
}
.write-box {
  border: none;
  width: 90%;
  height: 100px;
  padding: 15px;
  margin: auto;
  display: block;
  outline: none;
}
</style>
