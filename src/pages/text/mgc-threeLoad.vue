<template>
  <div class="loading">
    <span style="animation-delay: 0s;">L</span>
    <span style="animation-delay: 0.1s;">o</span>
    <span style="animation-delay: 0.2s;">a</span>
    <span style="animation-delay: 0.3s;">d</span>
    <span style="animation-delay: 0.4s;">i</span>
    <span style="animation-delay: 0.5s;">n</span>
    <span style="animation-delay: 0.6s;">g</span>
  </div>
</template>

<script>
export default {
  name: 'mgcThreeLoad',
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
