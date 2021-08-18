<template>
  <div class="loading">
    <!-- <span style="animation-delay: 0s;">L</span>
    <span style="animation-delay: 0.1s;">o</span>
    <span style="animation-delay: 0.2s;">a</span>
    <span style="animation-delay: 0.3s;">d</span>
    <span style="animation-delay: 0.4s;">i</span>
    <span style="animation-delay: 0.5s;">n</span>
    <span style="animation-delay: 0.6s;">g</span> -->
    <span v-for="(item,index) in props_text" :style="{'animation-delay': index*props_delay+'s','animation-duration':props_duration+'s'}" :key="index">{{item}}</span>
  </div>
</template>

<script>
export default {
  name: 'mgcLadderLoad',
  props: {
    props_text: {
      default: 'mgcLadderLoad',
      type: String,
    },
    props_delay: {
      default: 0.1,
      type: Number,
    },
    props_duration: {
      default: 2,
      type: Number,
    },
  },
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
  animation: bulge infinite;
}

@keyframes bulge {
  50% {
    box-shadow: 0 20px 0 #eee;
    transform: translateY(-35px);
  }
}
</style>
