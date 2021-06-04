<template>

    <div class="header">
      <el-menu :default-active="activeIndex"  class="el-menu-demo" mode="horizontal" @select="handleSelect"
               background-color="#545c64" text-color="#fff" active-text-color= "#ffd04b" >

          <el-menu-item  v-for="(menu,index) in menus" :key="index" >
            <el-menu-item :index="menu.id" v-if="menu.menuType==='el-menu-item'" @click="button2(menu)" >{{ menu.name }}</el-menu-item>
            <el-submenu :index="menu.id" v-if="menu.menuType==='el-submenu'">
              <template #title>
                {{menu.name}}
              </template>
                <el-menu-item v-for="(button,index1) in menu.menus" :key="index1" >
                  <el-menu-item :index="button.id" v-if="button.menuType==='el-menu-item'">{{ button.name }}</el-menu-item>
                  <el-submenu  :index="button.id" v-if="button.menuType==='el-submenu'">
                    <template #title>{{ button.name }}</template>
                      <el-menu-item v-for="(button1,index2) in button.menus" :key="index2" :index="button1.id" @click="button2(menu)">
                        {{ button1.name }}
                      </el-menu-item>
                  </el-submenu>
                </el-menu-item>

            </el-submenu>

          </el-menu-item>

      </el-menu>
    </div>

</template>

<script>
export default {
  data() {
    return {
      activeIndex: '1',
      menus:[
        {menuType:'el-menu-item',isShow:true,name:'处理中心',id:'1'},
        {menuType:'el-submenu',isShow:true,name:'我的工作台',id:'2',menus:[
            {menuType:'el-menu-item',name:'选项1',isShow:true,id:'2.1'},
            {menuType:'el-menu-item',name:'选项2',isShow:true,id:'2.2'},
            {menuType:'el-menu-item',name:'选项3',isShow:true,id:'2.3'},
            {menuType:'el-submenu',name:'选项4',id:'2.4',menus:[
                {menuType:'el-menu-item',name:'选项1',isShow:true,id:'2.4.1'},
                {menuType:'el-menu-item',name:'选项2',isShow:true,id:'2.4.2'},
                {menuType:'el-menu-item',name:'选项3',isShow:true,id:'2.4.3'},
              ]},
            ]},
        {menuType:'el-menu-item',isShow:'false',name:'消息中心',id:'3'},
        {menuType:'el-menu-item',isShow:'true',name:'订单管理',url:'http://baidu.com',id:'4'}
      ]
    }
  },
  methods: {
    handleSelect(key, keyPath) {
      console.log(key, keyPath,this);
    }, button2(value){
      console.log(value.url);
    }
  }
}

</script>

<style>

.header{
  width: 100%;
}
.el-menu-demo{

}

</style>