<template>
  <div class="loading">
    <span v-for="(item,index) in props_text" :style="{'animation-delay': index*props_delay+'s','animation-duration':props_duration+'s'}" :key="index">{{item}}</span>
  </div>
</template>

<script>
export default {
  name: 'mgcThreeLoad',
  props: {
    props_text: {
      default: 'mgcThreeLoad',
      type: String,
    },
    props_delay: {
      default: 0.1,
      type: Number,
    },
    props_duration: {
      default: 1,
      type: Number,
    },
  },
};
</script>

<style lang="less" scoped>
.loading {
    display: flex;
    color: white;
    font-size: 5em;
    font-family: "Baloo Bhaijaan", cursive;
    text-transform: uppercase;
  span {
    text-shadow: 0 1px #bbb, 0 2px #bbb, 0 3px #bbb, 0 4px #bbb, 0 5px #bbb, 0 6px transparent, 0 7px transparent, 0 8px transparent, 0 9px transparent, 0 10px 10px rgb(0, 0, 0 ,0.4);
    transform: translateY(20px);
    animation: bounce 0.3s ease infinite alternate;
  }
}
@keyframes bounce {
  to {
    text-shadow: 0 1px #bbb, 0 2px #bbb, 0 3px #bbb, 0 4px #bbb, 0 5px #bbb, 0 6px #bbb, 0 7px #bbb, 0 8px #bbb, 0 9px #bbb, 0 50px 25px rgba(0, 0, 0, 0.2);
    transform: translateY(-20px);
  }
}
</style>
