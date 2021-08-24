<template>
  <div class="rotating-text">
    <p>
      <span v-for="(items,indexs) in data_textArry" :key="indexs" class="word alizarin">
        <span v-for="(item,index) in items" :key="index" :class="['letter',item.type]">{{item.value}}</span>
      </span>
    </p>
  </div>
</template>

<script>
export default {
  name: 'mgcTextRoll',
  props: {
    props_textArry: {
      default: () => ['mgc0', 'text1', 'roll2', 'word3', 'excels4'],
      type: Array,
    },
    props_intervalTime: {
      default: 4000,
      type: Number,
    },
  },
  data() {
    return {
      data_activeIndex: 0,
      data_textArry: [],
    };
  },
  methods: {
    setTimeInterval() {
      this.rotateText();
      if (this.local_setInterval) {
        clearTimeout(this.local_setInterval);
      }
      this.local_setInterval = setTimeout(() => {
        this.setTimeInterval();
      }, 4000);
    },
    rotateText() {
      this.data_textArry[this.data_activeIndex].forEach((item, index) => {
        setTimeout(() => {
          item.type = 'out';
        }, index * 80);
      });
      if (this.data_activeIndex > this.data_textArry.length - 2) {
        this.data_activeIndex = 0;
      } else {
        this.data_activeIndex++;
      }
      this.data_textArry[this.data_activeIndex].forEach((item, index) => {
        item.type = 'behind';
        setTimeout(() => {
          item.type = 'in';
        }, 340 + index * 80);
      });
    },
  },
  beforeDestroy() {
    if (this.local_setInterval) {
      clearTimeout(this.local_setInterval);
    }
  },
  watch: {
    props_textArry: {
      handler(value) {
        if (!value) {
          return [];
        }
        const local_stringArry = [];
        value.forEach((items, indexs) => {
          const local_children = [];
          items.split('').forEach((item, index) => {
            local_children.push({
              type: indexs === 0 ? 'in' : 'out',
              value: item,
            });
          });
          local_stringArry.push(local_children);
          this.data_textArry = local_stringArry;
        });
        this.data_activeIndex = 0;
        this.setTimeInterval();
      },
      immediate: true,
      deep: true,
    },
  },
};
</script>

<style scoped lang="less">

.rotating-text {
  font-family: Lato, sans-serif;
  font-weight: 600;
  font-size: 36px;
  color: red;
  transform: translateX(-80px);

  p {
    display: inline-flex;
    margin: 0;
    vertical-align: top;

    .word {
      position: absolute;
      display: flex;
      opacity: 1;

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
