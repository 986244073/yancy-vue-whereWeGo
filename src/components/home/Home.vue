<template>
  <div>
    <HomeHeader :city="city"></HomeHeader>
    <HomeSwiper :list="swiperList"></HomeSwiper>
    <HomeIcons ></HomeIcons>
    <HomeRecommend :list="recommendList"></HomeRecommend>
    <HomeWeekend :list="weekendList"></HomeWeekend>
  </div>
</template>

<script>
  import HomeHeader from './pages/Header'
  import HomeSwiper from './pages/Swiper'
  import HomeIcons from './pages/Icons'
  import HomeRecommend from './pages/Recommend'
  import HomeWeekend from './pages/Weekend'
  import axios from 'axios'

  export default {
    name: "Home",
    components: {
      HomeHeader,
      HomeSwiper,
      HomeIcons,
      HomeRecommend,
      HomeWeekend
    },
    data() {
      return {
        city: '',
        swiperList:[],
        iconsList: [],
        recommendList:[],
        weekendList:[]
      }
    },
    methods: {
      getHomeInfo() {
        axios.get('https://www.easy-mock.com/mock/5d331f2f70b5c8763d05c93d/WhereWeGo/json')
          .then(this.getHomeInfoSucc)
      },
      getHomeInfoSucc(res) {
        if (res.data) {
          this.city = res.data.city;
          this.swiperList=res.data.swiperList;
          this.iconsList=res.data.iconsList;
          this.recommendList=res.data.recommendList;
          this.weekendList=res.data.recommendList;
        }
      }
    },
    mounted() {
      this.getHomeInfo()
    }
  }
</script>

<style scoped>

</style>
