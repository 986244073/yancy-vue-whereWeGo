<template>
  <div>

    <div class="recommend-title">
      周末去哪儿
    </div>
    <ul>
      <li class="item border-bottom" v-for="item in recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img :src="item.imgUrl" alt="图片" class="item-img">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>


</template>

<script>
  export default {
    name: "Weekend",
    data() {
      return {
        recommendList: [{
          id: '0001',
          imgUrl: 'https://imgs.qunarzz.com/sight/source/1505/a2/78e4dbcfd45a6d.jpg_r_640x214_7a62b06a.jpg',
          title: '成都必打卡',
          desc: '成都的标志，也是现代人对老成都的记忆'
        }, {
          id: '0002',
          imgUrl: 'https://imgs.qunarzz.com/sight/source/1505/a2/78e4dbcfd45a6d.jpg_r_640x214_7a62b06a.jpg',
          title: '成都必打卡',
          desc: '成都的标志，也是现代人对老成都的记忆'
        }, {
          id: '0003',
          imgUrl: 'https://imgs.qunarzz.com/sight/source/1505/a2/78e4dbcfd45a6d.jpg_r_640x214_7a62b06a.jpg',
          title: '成都必打卡',
          desc: '成都的标志，也是现代人对老成都的记忆'
        }, {
          id: '0004',
          imgUrl: 'https://imgs.qunarzz.com/sight/source/1505/a2/78e4dbcfd45a6d.jpg_r_640x214_7a62b06a.jpg',
          title: '成都必打卡',
          desc: '成都的标志，也是现代人对老成都的记忆'
        },

        ]
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

  .item-img-wrapper {
    overflow: hidden;
    height: 0;
    padding-bottom: 33.9%;
  }

  .item img {
    width: 100%;

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
</style>
