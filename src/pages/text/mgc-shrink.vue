<template>
  <div class="abbr">
    <span v-for="(item,index) in com_text" :key="index" :class="item.type">{{item.value}}</span>
  </div>
</template>

<script>
export default {
  name: 'mgcShrink',
  props: {
    props_textArry: {
      default: () => ['Mgc', 'Shrink', 'Show'],
      type: Array,
    },
  },
  computed: {
    com_text() {
      if (!this.props_textArry) {
        return [];
      }
      const local_stringArry = [];
      this.props_textArry.forEach((items) => {
        items.split('').forEach((item, index) => {
          local_stringArry.push({
            type: index === 0 ? 'initial' : 'hidden',
            value: item,
          });
        });
      });
      return local_stringArry;
    },
  },
};
</script>

<style scoped lang="less">

.abbr {
  display: flex;
  font-size: 2em;
  font-weight: bold;
  font-family: Lato, sans-serif;
  text-decoration: none;
  cursor: pointer;
  span {
    text-decoration: underline #999;
    transition: all 0.5s ease-in-out;
    &.hidden {
      max-width: 0;
      text-decoration: none;
      opacity: 0;
    }
  }

  &:hover {
    span {
      max-width: 2em;
      text-decoration: none;
      opacity: 1;

      &.initial {
        margin-left: 0.5em;
      }
    }
  }
}


</style>
