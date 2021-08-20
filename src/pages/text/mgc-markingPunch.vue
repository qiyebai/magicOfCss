<template>
  <p class="shining">{{this.props_text}}</p>
</template>

<script>
export default {
  name: 'mgcMarkingPunch',
  props: {
    props_text: {
      default: 'mgcMarkingPunch',
      type: String,
    },
  },
};
</script>

<style scoped lang="less">
.shining {
   --fill-color: #198CE6;
      position: relative;
      display: block;
      padding: 4px 0;
      font: 700 3rem Raleway;
      text-decoration: none;
      text-transform: uppercase;
      -webkit-text-stroke: 2px var(--fill-color);
      background: linear-gradient(var(--fill-color) 0 100%) left / 0 no-repeat;
      color: transparent;
      background-clip: text;
      transition: 0.5s linear;

      &:hover {
        background-size: 100%;
      }
}
</style>
