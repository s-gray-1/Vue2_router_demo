<template>
  <div class="movie-container">
    <!-- this.$route 是路由的"参数对象" -->
    <!-- this.$router 是路由的"导航方式" -->
    <h3>Movie 组件---{{ $route.params.mid }}</h3>
    <h3>Movie 组件---{{ mid }}</h3>
    <button @click="showThis">打印this</button>
    <button @click="goback">后退</button>
    <!-- 在行内使用编程式导航 要去掉this -->
    <button @click="$router.back()">back后退</button>
    <button @click="$router.forward()">forward前进</button>
  </div>
</template>

<script>
export default {
  name: 'Movie',
  // 接受props数据
  props:['mid'],
  methods:{
    showThis(){
      console.log(this);
    },
    goback(){
      this.$router.go(-1)
      // 如果后退的层数超过上限 则原地不动
    }
  }
  

}
</script>

<style lang="less" scoped>
.movie-container {
  min-height: 200px;
  background-color: lightsalmon;
  padding: 15px;
}
</style>
