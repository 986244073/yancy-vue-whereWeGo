<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <i class="iconfont icon-icon-test3 header-back"></i>

    </router-link>

  </div>
</template>

<script>
  export default {
    name: "Header"
  }
</script>

<style scoped>
  .header {
    position: relative;
    overflow: hidden;
    height: .86rem;
    line-height: .86rem;
    text-align: center;
    color: white;
    background: #00bcd4;
    font-size: .32rem;
  }
  .header-back{
    color: white;
    position: absolute;
    top: 0;
    left: 0;
    width: .64rem;
    text-align: center;
    font-size: .4rem;
  }
</style>
