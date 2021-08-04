<template>
  <div class="title-content">
    <span style="animation-delay: 519ms;">智</span>
    <span style="animation-delay: 19ms;">能</span>
    <span style="animation-delay: 649ms;">编</span>
    <span style="animation-delay: 259ms;">排</span>
    <span style="animation-delay: 139ms;">与</span>
    <span style="animation-delay: 489ms;">协</span>
    <span style="animation-delay: 569ms;">同</span>
    <span style="animation-delay: 229ms;">响</span>
    <span style="animation-delay: 149ms;">应</span>
    <span style="animation-delay: 69ms;">平</span>
    <span style="animation-delay: 439ms;">台</span>
  </div>
</template>

<script>
export default {
  name: 'mgcGradual',
};
</script>

<style lang="less" scoped>
.title-content{
  span{
    opacity: 0;
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
