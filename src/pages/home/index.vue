<template>
  <div class="phone">
    <div class="tool">
      <Button :disabled="data_index===0" @click="getImg('up')">上一张</Button>
      <Button :disabled="data_index===data_picture.length-1" @click="getImg('down')">下一张</Button>
    </div>
    <div class="data">{{com_birthTime}}</div>
    <div class="data">{{data_picture[data_index].data}}</div>
    <ul class="menu">
      <li v-for="(item,index) in data_picture" :key="index" :id="index" :class="data_index===index?'active':''" @click="choose(index)">
        {{item.time}}
      </li>
    </ul>
    <div class="content">
      <div class="picture">
        <img :src="'images/'+data_picture[data_index].url" alt="">
      </div>
    </div>
  </div>
</template>

<script>
const picture = [];
const context = require.context('../../../public/images/', true, /[\w.]+\.jpg/);
context.keys().forEach((key) => {
  const fullPath = key.substring(2).split('.');
  picture.push({
    time: fullPath[0].slice(0, 10),
    url: key.substring(2),
    data: `${fullPath[0].substring(0, 4)}年${fullPath[0].slice(5, 7)}月${fullPath[0].slice(8, 10)}日`,
  });
});
export default {
  data() {
    return {
      data_picture: picture,
      data_index: 20,
    };
  },
  mounted() {
    // setInterval(() => {
    //   this.data_index++;
    // }, 1000);
  },
  computed: {
    com_birthTime() {
      const local_birthTime = (new Date(this.data_picture[this.data_index].time).getTime() - new Date('2021-09-13').getTime()) / (1000 * 60 * 60 * 24);
      if (local_birthTime < 0) {
        return `距离出生还有${-local_birthTime}天`;
      }
      return `我已经出生${local_birthTime}天`;
    },
  },
  methods: {
    getImg(type) {
      if (type === 'up') {
        this.data_index--;
      } else {
        this.data_index++;
      }
      document.getElementById(this.data_index).scrollIntoView();
    },
    choose(index) {
      this.data_index = index;
    },
  },
};
</script>

<style lang="less" scoped>
.content{
  display: flex;
  justify-content: center;
}
.picture{
  width: 600px;
  max-width: 100%;
  img{
    width:100%;
  }
}
.tool{
  width: 200px;
  display: flex;
  margin: 0 auto;
  justify-content: space-between;
  padding-top: 20px;
}
.data{
  text-align: center;
  font-size: 20px;
  line-height: 32px;
}
.menu{
  position: fixed;
  max-height: 100vh;
  overflow: auto;
  top: 0;
  width: 200px;
  line-height: 32px;
  text-align: center;
  li{
    cursor: pointer;
    border:1px solid #dfdfdf;
    border-radius: 8px;
    margin: 4px auto;
    width: 80%;
    list-style: none;
    &.active{
        background: #1f5aff;
        color: #fff;
      }
      &:hover{
        background: #1f5aff;
        color: #fff;
      }
 }
}
@media screen and (max-width: 800px) {
  .menu{
    position: relative;
    width: inherit;
    white-space: nowrap;
    padding-bottom: 10px;
    li{
      width: 100px;
      display: inline-block;
      text-align: center;
      // background: #1f5aff;
      // color: #fff;
      margin: 0 4px;
    }
  }
}
</style>
