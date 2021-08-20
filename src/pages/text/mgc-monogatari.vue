<template>
  <p class="shining">{{this.props_text}}</p>
</template>

<script>
export default {
  name: 'mgcMonogatari',
  props: {
    props_text: {
      default: 'mgcMonogatari',
      type: String,
    },
  },
};
</script>

<style scoped>
.shining {
  font-size: 2em;
  letter-spacing: 4px;
  text-transform: uppercase;
  background: linear-gradient(90deg, rgba(0,0,0,1) 0%, rgba(255,255,255,1) 50%, rgba(0,0,0,1) 100%);
  background-size: 80%;
  background-repeat: no-repeat;
  color: transparent;
  background-clip: text;
  animation: shining 3s linear infinite;
}

@keyframes shining {
  from {
    background-position: -500%;
  }
  to {
    background-position: 500%;
  }
}
</style>
