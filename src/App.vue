<!--根组件-->

<!--html模版-->
<template>
  <div id="app">
    <el-container>
      <Header></Header>
    </el-container>
  </div>
</template>

<!--js块-->
<script>
//引入自定义
import Header from "./components/Header";


export default {
  components: {
    Header
  }
}
</script>

<!--样式-->
<style>
@import url("//unpkg.com/element-plus/lib/theme-chalk/index.css");

</style>