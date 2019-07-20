<template>
  <div>
    <HomeHeader></HomeHeader>
    <HomeSwiper></HomeSwiper>
    <HomeIcons></HomeIcons>
    <HomeRecommend></HomeRecommend>
    <HomeWeenkend></HomeWeenkend>
  </div>
</template>

<script>
  import HomeHeader from './pages/Header'
  import HomeSwiper from './pages/Swiper'
  import HomeIcons from './pages/Icons'
  import HomeRecommend from './pages/Recommend'
  import HomeWeenkend from './pages/Weekend'

  export default {
    name: "Home",
    components: {
      HomeHeader,
      HomeSwiper,
      HomeIcons,
      HomeRecommend,
      HomeWeenkend
    }
  }
</script>

<style scoped>

</style>
