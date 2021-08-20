<template>
  <div id="app">
    <router-view></router-view>
    <!-- <canvas id="myCanvas"></canvas> -->
  </div>
</template>

<script>
// import { init } from './views/index';

export default {
  name: 'App',
};
</script>

<style lang="less">
#app {
  font-family: "pingfang-thin";
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
}
li,ul{
  list-style: none;
}
</style>
