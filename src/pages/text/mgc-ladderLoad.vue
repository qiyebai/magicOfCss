<template>
  <div class="loading">
    <span style="animation-delay: 0s;">L</span>
    <span style="animation-delay: 0.1s;">o</span>
    <span style="animation-delay: 0.2s;">a</span>
    <span style="animation-delay: 0.3s;">d</span>
    <span style="animation-delay: 0.4s;">i</span>
    <span style="animation-delay: 0.5s;">n</span>
    <span style="animation-delay: 0.6s;">g</span>
  </div>
</template>

<script>
export default {
  name: 'mgcLadderLoad',
};
</script>

<style lang="less" scoped>
.loading {
  display: flex;
  color: white;
  font-size: 3em;
  text-transform: uppercase;
}
.loading span {
  padding: 0 20px;
  line-height: 100px;
  background: #34495e;
  animation: bulge 2s infinite;
}

@keyframes bulge {
  50% {
    box-shadow: 0 20px 0 #eee;
    transform: translateY(-35px);
  }
}
</style>
