<template>
  <div class="search">
    <input type="text"
           placeholder="输入城市名或者拼音"
           class="search-input"
    >
  </div>
</template>

<script>
  export default {
    name: "Search"
  }
</script>

<style scoped>
  .search {
    height: .86rem;
    padding: .1rem;
    background: #00bcd4;
  }

  .search-input {
    box-sizing: border-box;
    height: .82rem;
    width: 100%;
    line-height: .82rem;
    text-align: center;
    border-radius: .06rem;
    color: #666;
  }
</style>
