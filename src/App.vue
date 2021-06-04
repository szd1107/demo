<!--根组件-->

<!--html模版-->
<template>
  <div id="app">
    <el-container>
      <el-header>
        <div class="logo left">
          <a href="javascript:void(0)" target="_blank">
            <img src="./assets/logo.png">
          </a>
        </div>
        <div class="person_info right" style="line-height: 48px">
          <a>我的信息</a>
        </div>
      </el-header>
      <el-container>
        <el-aside><Menu></Menu></el-aside>
        <el-main>
          MAIN
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<!--js块-->
<script>
//引入自定义
import Menu from "./components/Menu";

export default {
  components: {
    Menu
  }
}
</script>

<!--样式-->
<style>
.left {
  float: left;
}

.right {
  float: right;
}

.el-container {
  height: 100%;
}


.el-header {
  height: 48px;
  background-color: #2459a2;
  color: white;
  text-align: center;

}

.el-header .logo a img {
  width: 45px;
  height: 45px;
}




</style>