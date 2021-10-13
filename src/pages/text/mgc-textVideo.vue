<template>
  <div class="content">
    <video autoplay muted loop preload>
      <source :src="props_videoUrl" />
    </video>
    <h1>{{this.props_text}}</h1>
  </div>
</template>

<script>
export default {
  name: 'mgcTextVideo',
  props: {
    props_text: {
      default: 'VIDEO',
      type: String,
    },
    props_videoUrl: {
      default: 'images/ocean.mp4',
      type: String,
    },
  },
};
</script>

<style scoped lang="less">
.content{
  position: relative;
  width: 100%;
  height: 100%;
  video,
  h1 {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    margin: 0;
  }
  video {
    object-fit: cover;
  }
  h1 {
    font-size: 170px;
    font-weight: 700;
    text-transform: uppercase;
    text-align: center;
    background: white;
    mix-blend-mode: screen;
  }
}


</style>
