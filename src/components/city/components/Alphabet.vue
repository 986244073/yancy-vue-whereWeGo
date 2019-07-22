<template>
  <div class="list">
    <ul>
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: "Alphabet"
  }
</script>

<style scoped lang="stylus">
  @import "~@/assets/var.styl"
  .list
    display: flex
    flex-direction: column
    justify-content: center
    position: absolute
    top: 1.58rem
    right: 0
    bottom: 0
    width: .4rem
    .item
      line-height :.44rem
      text-align :center
      color: #00bcd4
</style>
