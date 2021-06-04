<!--问候组件-->
<template>
  <div>
    <p class="message">{{msg}}</p>
  </div>
</template>

<script>
  //配置对象
  export default {
    //必须写函数
    data(){
      return {
        msg: 'Hello Vue Component'
      }
    }
  }

</script>

<style>
  .message{
    color: rebeccapurple;
    font-size: 18px;
  }

</style>