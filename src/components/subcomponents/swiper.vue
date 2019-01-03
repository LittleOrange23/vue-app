<template>
  <div>
    <!-- 轮播图组件 -->
    <mt-swipe :auto="2000">
      <mt-swipe-item v-for="(item, index) in lunbotuList" :key="index">
        <img :src="item" :class="{'full': isfull}">
      </mt-swipe-item>
    </mt-swipe>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // 存储轮播图中图片的数组
      lunbotuList: [
        require('../../images/lunbotu1.jpg'),
        require('../../images/lunbotu2.jpg'),
        require('../../images/lunbotu3.jpg'),
      ]
    }
  },
  // 父传子组件，用于判断轮播图中的图片是否使用100%
  props: ["isfull"]
};
</script>

<style lang="scss" scoped>
.mint-swipe {
  height: 200px;

  .mint-swipe-item {
    text-align: center;

    img {
      height: 100%;
    }
  }
}

.full {
  width: 100%;
}
</style>
