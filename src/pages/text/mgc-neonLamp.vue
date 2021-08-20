<template>
  <div class="rainbow">
    <span v-for="(item,index) in props_text" :style="{'animation-delay': index*props_delay+'s','animation-duration':props_duration+'s'}" :key="index">{{item}}</span>
  </div>
</template>

<script>
export default {
  name: 'mgcNeonLamp',
  props: {
    props_text: {
      default: 'mgcNeonLamp',
      type: String,
    },
    props_delay: {
      default: 0.1,
      type: Number,
    },
    props_duration: {
      default: 10,
      type: Number,
    },
  },
};
</script>

<style lang="less" scoped>
.rainbow {
  letter-spacing: 0.2rem;
  font-size: 1.2rem;
  text-transform: uppercase;
  span {
    animation: rainbow 50s alternate infinite forwards;
  }
}

@keyframes rainbow {
  0% {
      color: #a9ef8f;
  }
  5% {
      color: #acef8f;
  }
  10% {
      color: #e2ef8f;
  }
  15% {
      color: #d18fef;
  }
  20% {
      color: #ae8fef;
  }
  25% {
      color: #8fdcef;
  }
  30% {
      color: #efc18f;
  }
  35% {
      color: #a98fef;
  }
  40% {
      color: #dcef8f;
  }
  45% {
      color: #bcef8f;
  }
  50% {
      color: #ef948f;
  }
  55% {
      color: #9fef8f;
  }
  60% {
      color: #ef8f93;
  }
  65% {
      color: #8fefd4;
  }
  70% {
      color: #8fefae;
  }
  75% {
      color: #efaf8f;
  }
  80% {
      color: #8fefe6;
  }
  85% {
      color: #8fefc4;
  }
  90% {
      color: #ef8fe7;
  }
  95% {
      color: #8fceef;
  }
  100% {
      color: #ef8fd4;
  }
}

</style>
