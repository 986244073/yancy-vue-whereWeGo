<template>
  <div class="header">
    <div class="header-left">
      <span><i class="  iconfont icon-icon-test3"></i>
      </span>
    </div>
    <div class="header-search">
      <i class=" icon iconfont icon-icon-test"></i>
      输入城市/景点/游玩主题
    </div>

    <div class="header-right">
      北京
      <i class=" icon iconfont icon-icon-test4"></i>

    </div>

  </div>
</template>

<script>
  export default {
    name: "Header"
  }
</script>

<style scoped lang="stylus">
  @import "~@/assets/var.styl"
  .header {
    width: 100%;
    line-height: .88rem;
    /*background: #00bcd4;*/
    background: $bgColor;
    color: $textColor;
    font-size: .36rem;
    display: flex;
  }

  .header-left {
    width: .4rem;
    padding: 0 .2rem;
    text-align: center;
    font-weight: bold;
  }

  .header-search {
    flex: 1;
    background: #fff;
    height: .6rem;
    margin: .15rem 0;
    border-radius: .1rem;
    color: #e4e7ea;
    line-height: .6rem;
    font-size: .28rem;
  }

  .header-right {
    font-size: .28rem;
    padding: 0 .2rem;
  }
</style>
