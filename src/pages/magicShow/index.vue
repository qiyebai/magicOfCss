<template>
  <div>
    <ul class="lists">
      <li v-for="(item,index) in data_lists" :key="index" class="lists-item">
        <div class="show">
          <component :is="item.name">
            <div style="color:#aaa">我是slot</div>
          </component>
        </div>
        <div class="name">{{item.name}}</div>
      </li>
    </ul>
  </div>
</template>

<script>
const context = require.context('../../pages/', true, /mgc-[\w.]+\.vue/);
// eslint-disable-next-line no-var
var local_Lists = [];
const install = () => {
  context.keys().forEach((key) => {
    const component = context(key).default;
    const fullPath = key.substring(2).split('/mgc-')[1];
    const path = fullPath.split('.vue')[0];
    const fullPathed = key.substring(2);
    local_Lists.push({
      name: component.name,
    });
  });
};
install();
export default {
  data() {
    return {
      data_lists: local_Lists,
    };
  },
};
</script>

<style lang="less" scoped>
.lists{
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  .lists-item{
    width: 48%;
    margin: 10px;
    .show{
      border:1px solid #eee;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 200px;
    }
    .name{
      text-align: center;
      line-height: 30px;
      font-size: 20px;
    }
  }
}
</style>
