<template>
  <div>

    <div class="recommend-title">
      热销推荐
    </div>
    <ul>
      <li class="item border-bottom" v-for="item in list" :key="item.id">
        <div class="item-img-wrapper">
          <img :src="item.imgUrl" alt="图片" class="item-img">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>


</template>

<script>
  export default {
    name: "Recommend",
    props: {
      list: Array
    },
    data() {
      return {
        // recommendList: [{
        //   id: '0001',
        //   imgUrl: 'https://imgs.qunarzz.com/sight/p0/1612/1d/1d9a740c1f9e0efaa3.img.jpg_200x200_63285bd9.jpg',
        //   title: '成都海昌极地海洋公园',
        //   desc: '莫的啥子好看的'
        // }, {
        //   id: '0002',
        //   imgUrl: 'https://imgs.qunarzz.com/sight/p0/1612/1d/1d9a740c1f9e0efaa3.img.jpg_200x200_63285bd9.jpg',
        //   title: '成都海昌极地海洋公园',
        //   desc: '莫的啥子好看的'
        // }, {
        //   id: '0003',
        //   imgUrl: 'https://imgs.qunarzz.com/sight/p0/1612/1d/1d9a740c1f9e0efaa3.img.jpg_200x200_63285bd9.jpg',
        //   title: '成都海昌极地海洋公园',
        //   desc: '莫的啥子好看的'
        // }, {
        //   id: '0004',
        //   imgUrl: 'https://imgs.qunarzz.com/sight/p0/1612/1d/1d9a740c1f9e0efaa3.img.jpg_200x200_63285bd9.jpg',
        //   title: '成都海昌极地海洋公园',
        //   desc: '莫的啥子好看的'
        // },
        //
        // ]
      }
    },
  }
</script>

<style scoped>
  .recommend-title {
    margin-top: .2rem;
    line-height: .8rem;
    background: #eee;
    text-indent: .2rem;
    font-size: .5rem;
  }

  .item {
    display: flex;
    height: 1.9rem;
    overflow: hidden;
  }

  .item img {
    width: 1.7rem;
    height: 1.7rem;
    padding: 0.1rem;
  }

  .item-info {
    flex: 1;
    padding: .1rem;
    min-width: 0;
  }

  .item-title {
    line-height: .40rem;
    font-size: .32rem;
  }

  .item-desc {
    line-height: .4rem;
    color: #ccc;
    font-size: .3rem;
  }

  .item-button {
    line-height: .44rem;
    color: white;
    background: #ff9300;
    border-radius: .06rem;
    padding-top: .1rem;
  }
</style>
