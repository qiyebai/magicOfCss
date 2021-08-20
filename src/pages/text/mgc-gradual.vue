<template>
  <div class="title-content">
    <span v-for="(item,index) in props_text" :style="{'animation-delay': parseInt(Math.random()*500)+'ms'}" :key="index">{{item}}</span>
  </div>
</template>

<script>
export default {
  name: 'mgcGradual',
  text: '参数名称:props_text,类型:字符串',
  props: {
    props_text: {
      default: 'mgcGradual',
      type: String,
    },
  },
};
</script>

<style lang="less" scoped>
.title-content{
  span{
    opacity: 0;
    font-size: 30px;
    filter: blur(10px);
    animation: fadeIn 2s alternate infinite;
  }
}
@keyframes fadeIn{
  50%,100%{
    opacity: 1;
    filter: blur(0px)
  }
}
</style>
