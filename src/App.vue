<!--根组件-->

<!--html模版-->
<template>
  <div id="app">
    <el-container>
      <Header></Header>
      <el-aside width=”200px”> <Menu></Menu></el-aside>

    </el-container>
  </div>
</template>

<!--js块-->
<script>
//引入自定义
import Header from "./components/Header";
import Menu from "./components/Menu";

export default {
  components: {
    Header,Menu
  }
}
</script>

<!--样式-->
<style>
@import url("//unpkg.com/element-plus/lib/theme-chalk/index.css");

</style>