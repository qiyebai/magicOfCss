<template>
  <p class="loading" :style="{'box-shadow':'inset 0.5em -0.5em '+props_color}"></p>
</template>

<script>
export default {
  name: 'mgcRunLoad',
  props: {
    props_color: {
      default: 'crimson',
      type: String,
    },
  },
};
</script>

<style scoped lang="less">

.loading {
  position: relative;
  width: 8em;
  height: 8em;
  border-radius: 50%;
  animation: spin 2s linear infinite;

  &::before,
  &::after {
    position: absolute;
    content: "";
    width: 100%;
    height: 100%;
    background: inherit;
    border-radius: inherit;
    box-shadow: inherit;
  }

  &::before {
    filter: blur(5px);
  }

  &::after {
    filter: blur(10px);
  }
}

@keyframes spin {
  to {
    transform: rotate(1turn);
  }
}

</style>
