<template>
  <div class="rotating-text">
    <p>
      <span v-for="(item,index) in props_textArry" :key="index" class="word alizarin">{{item}}</span>
    </p>
  </div>
</template>

<script>
export default {
  name: 'mgcTextRoll',
  props: {
    props_textArry: {
      default: () => ['mgc', 'text', 'roll'],
      type: Array,
    },
  },
};
</script>

<style scoped lang="less">

.rotating-text {
  font-family: Lato, sans-serif;
  font-weight: 600;
  font-size: 36px;
  color: white;
  transform: translateX(-80px);

  p {
    display: inline-flex;
    margin: 0;
    vertical-align: top;

    .word {
      position: absolute;
      display: flex;
      opacity: 0;

      .letter {
        transform-origin: center center 25px;

        &.out {
          transform: rotateX(90deg);
          transition: 0.32s cubic-bezier(0.6, 0, 0.7, 0.2);
        }
        &.in {
          transition: 0.38s ease;
        }
        &.behind {
          transform: rotateX(-90deg);
        }
      }
    }
  }
}

.alizarin {
  color: #e74c3c;
}

.wisteria {
  color: #8e44ad;
}

.peter-river {
  color: #3498db;
}

.emerald {
  color: #2ecc71;
}

.sun-flower {
  color: #f1c40f;
}
</style>
