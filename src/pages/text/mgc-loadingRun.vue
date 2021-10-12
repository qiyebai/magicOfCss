<template>
  <div class="loading-run"></div>
</template>

<script>
export default {
  name: 'mgcLoadingRun',
  props: {
    props_text: {
      default: 'mgcShineButton',
      type: String,
    },
  },
};
</script>

<style lang="less" scoped>
.loading-run {
    position: relative;
    margin: auto;
    width: 150px;
    height: 150px;
    --colorA: #b78eff;
    &::before,
    &::after {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;
        border-radius: 50%;
        border-top: 5px solid #fff;
        filter:
          drop-shadow(0 0 2px var(--colorA))
          drop-shadow(0 0 5px var(--colorA))
          drop-shadow(0 0 10px var(--colorA))
          drop-shadow(0 0 20px var(--colorA));
        animation: rotate 3s infinite linear;
    }
    &::after {
        --colorA: #ffec41;
        animation-delay: -1.5s;
    }
}
@keyframes rotate {
    100% {
        transform: rotate(360deg);
    }
}
</style>
