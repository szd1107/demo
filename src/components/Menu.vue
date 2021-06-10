<template>
<!--  <el-row class="tac">
  <el-col :span="12">
    <el-menu
        default-active="2"
        class="el-menu-vertical-demo"
        @open="handleOpen"
        @close="handleClose" style="width: 200px">
      <el-submenu index="1" >
        <template #title >
          <i class="el-icon-location"></i>
          <span>导航一</span>
        </template>
        <el-menu-item-group>
          <template #title>分组一</template>
          <el-menu-item index="1-1">选项1</el-menu-item>
          <el-menu-item index="1-2">选项2</el-menu-item>
        </el-menu-item-group>
        <el-menu-item-group title="分组2">
          <el-menu-item index="1-3">选项3</el-menu-item>
        </el-menu-item-group>
        <el-submenu index="1-4">
          <template #title>选项4</template>
          <el-menu-item index="1-4-1">选项1</el-menu-item>
        </el-submenu>
      </el-submenu>
      <el-menu-item index="2">
        <i class="el-icon-menu"></i>
        <template #title>导航二</template>
      </el-menu-item>
      <el-menu-item index="3" disabled>
        <i class="el-icon-document"></i>
        <template #title>导航三</template>
      </el-menu-item>
      <el-menu-item index="4">
        <i class="el-icon-setting"></i>
        <template #title>导航四</template>
      </el-menu-item>
      <el-submenu index="5">
        <template #title>
          <i class="el-icon-location"></i>
          <span>导航一</span>
        </template>
        <el-menu-item-group>
          <template #title>分组一</template>
          <el-menu-item index="5-1">选项1</el-menu-item>
          <el-menu-item index="5-2">选项2</el-menu-item>
        </el-menu-item-group>
        <el-menu-item-group title="分组2">
          <el-menu-item index="5-3">选项3</el-menu-item>
        </el-menu-item-group>
      </el-submenu>
    </el-menu>
  </el-col>
</el-row>-->

  <div>
    <component class="menu-item" v-for="(value) in navList" :key="value.title+value.url"
               :index="value.url"
               :is="(value.children&&value.children.length>0)?'el-submenu':'el-menu-item'">
      <template slot="title">
        <i :class="[value.icon]"></i>
        <span>{{value.title}}</span>
      </template>
      <template v-if="value.children&&value.children.length>0">
        <nav-menu :navList="value.children"></nav-menu>
      </template>
    </component>
  </div>

</template>

<script>
export default {
  data(){
    return {
      userInfo:{
        username: '',
      },
        isCollapse: false,
        navList: [{
          icon: 'el-icon-document',
          title: '订单管理',
          url: '/OrderManage'
        },{
          icon: 'el-icon-dish',
          title: '菜单管理',
          url: '/ProductManage'
        },{
          icon: 'el-icon-suitcase',
          title: '店铺管理',
          url: "suibianxie",
          children: [{
            icon: 'el-icon-tickets',
            title: '店铺资料',
            url: '/StoreProfile'
          },{
            icon: 'el-icon-picture-outline',
            title: '轮播图管理',
            url: '/BannerPicture'
          },{
            icon: 'el-icon-s-grid',
            title: '桌台管理',
            url: '/TableManage'
          },{
            icon: 'el-icon-s-grid',
            title: '测试',
            url: "suibianxie2",
            children: [{
              icon: 'el-icon-s-grid',
              title: '测试1',
              url: '/TableManage'
            }]
          }]
        },{
          icon: 'el-icon-setting',
          title: '账号管理',
          url: '/AccountManage'
        },{
          icon: 'el-icon-user',
          title: '个人资料',
          url: '/PersonProfile'
        }]
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