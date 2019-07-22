<template>
  <div class="list">
    <ul>
      <li
        class="item"
        v-for="(item ,index) of cities"
        :key="index"
        @click="handleLetterClick"
      >
        {{index}}
      </li>

    </ul>
  </div>
</template>

<script>
  export default {
    name: "Alphabet",
    props: {
      cities: {
        type: Object,
      },
    },
    methods: {
      handleLetterClick(e) {
        this.$emit('change', e.target.innerHTML);
      }
    }
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
      line-height: .44rem
      text-align: center
      color: #00bcd4
</style>
