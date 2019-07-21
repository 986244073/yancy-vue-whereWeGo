<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="page in pages" :key="page.id">
        <div class="icons-item" v-for="item in page" :key="item.id">
          <img :src="item.imgUrl" :alt="item.title">
          <p>{{item.title}}</p>
        </div>
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>


  </div>
</template>

<script>
  import 'swiper/dist/css/swiper.css'////这里注意具体看使用的版本是否需要引入样式，以及具体位置。
  import {swiper, swiperSlide} from 'vue-awesome-swiper'
  import axios from 'axios'

  export default {
    name: "Icons",
    created(){
      axios.get('https://www.easy-mock.com/mock/5d331f2f70b5c8763d05c93d/WhereWeGo/json')
        .then(response => {
          this.iconsList = response.data.iconsList;
          console.log(this.iconsList);
        }).catch(error => {
          console.log(error);
          alert('网络错误')
        })
    },
    data() {
      return {
        iconsList: [
          //   {
          //     id: "01",
          //     imgUrl: "https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png"
          //     , title: "景点门票"
          //   }, {
          //     id: "02",
          //     imgUrl: "https://imgs.qunarzz.com/piao/fusion/1803/4d/a1eda1a2b8414302.png"
          //     , title: "暑期夜场"
          //
          //   }, {
          //     id: "03",
          //     imgUrl: "https://imgs.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png"
          //     , title: "成都比游"
          //
          //   }, {
          //     id: "04",
          //     imgUrl: "https://imgs.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png"
          //     , title: "川剧变脸"
          //
          //   }, {
          //     id: "05",
          //     imgUrl: "https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/a40ee278d67000f2a29d2e20f6a029b3.png"
          //     , title: "自然风光"
          //
          //   }, {
          //     id: "06",
          //     imgUrl: "https://imgs.qunarzz.com/piao/fusion/1803/b8/c5dcdb58deec2402.png"
          //     , title: "碧峰峡"
          //
          //   }, {
          //     id: "07",
          //     imgUrl: "https://imgs.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png"
          //     , title: "游乐场"
          //
          //   }, {
          //     id: "08",
          //     imgUrl: "https://imgs.qunarzz.com/piao/fusion/1803/54/35899492b1302802.png"
          //     , title: "熊猫基地"
          //
          //   }, {
          //     id: "09",
          //     imgUrl: "https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/57489034f410bdc823e7fa1b9e82dfd4.png"
          //     , title: "清凉一夏"
          //
          //   }, {
          //     id: "10",
          //     imgUrl: "https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/f04285731d7121da1b9028e2bf431695.png"
          //     , title: "都江堰"
          //   },
        ],
        swiperOption: {
          pagination: {
            el: '.swiper-pagination'
          },
          loop: true
        }
      }
    },
    components: {
      swiper,
      swiperSlide
    },
    computed: {
      pages() {
        let pages = [];
        this.iconsList.forEach((item, index) => {
          let page = Math.floor(index / 8);
          if (!pages[page]) {
            pages[page] = [];
          }
          pages[page].push(item);
        });
        return pages;
      },
      // showList(){
      //   return this.list1;
      // },
      swiper() {
        return this.$refs.mySwiper.swiper
      },
      mounted() {
        // current swiper instance
        // 然后你就可以使用当前上下文内的swiper对象去做你想做的事了
        console.log('this is current swiper instance object', this.swiper);
        this.swiper.slideTo(3, 1000, false)
      }
    }
  }
</script>

<style scoped>
  .icons {
    padding-top: .1rem;
    width: 100%;
    overflow: hidden;
  }

  .icons-item {
    width: 25%;
    padding-bottom: 25%;
    height: 0;
    float: left;
  }

  .icons-item img {
    width: 1.1rem;
    height: 1.1rem;
    display: block;
    margin: 0 auto;
    padding-top: .1rem;
  }

  .icons-item p {
    font-size: .28rem;
    margin-top: .1rem;
    text-align: center;
    color: #212121;
  }
</style>
