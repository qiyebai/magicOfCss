<template>
  <div class="scene">
    <div class="card">
      <div class="card__face card__face--front">
        <img class="img" :src="props_img" />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'mgcInverted',
  props: {
    props_img: {
      default: '/images/imgs.jpg',
      type: String,
    },
  },
};
</script>
<style lang="less" scoped>

.scene {
  display: flex;
  justify-content: space-between;
  .card {
    position: relative;
    width: 140px;
    height: 80px;
    .card__face {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      -webkit-box-reflect: below 0 linear-gradient(transparent, transparent, rgba(0, 0, 0, 0.4));
      .img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }
}
</style>
