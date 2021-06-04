<!--问候组件-->
<template>
  <el-aside>
    <el-menu :default-openeds="['1', '2']">
      <el-submenu index="1">
        <template #title><i class="el-icon-message"></i>导航一</template>

          <el-menu-item index="1-1">选项1</el-menu-item>
          <el-menu-item index="1-2">选项2</el-menu-item>
          <el-menu-item index="1-3">选项3</el-menu-item>

        <el-submenu index="1-4">
          <template #title>选项4</template>
          <el-menu-item index="1-4-1">选项4-1</el-menu-item>
        </el-submenu>
      </el-submenu>

    </el-menu>
  </el-aside>
</template>

<script>
export default {
  data(){
      return{
        menus:[
          {

          }
        ]
      }
  }
}
</script>

<style>
.el-aside {
  position: fixed;
  top: 60px;
  left: 0;
  bottom: 0;
  width: 200px;
  height: 100%;
  background-color: rgb(238, 241, 246);
}
</style>