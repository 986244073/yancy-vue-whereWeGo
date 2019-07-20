<template>
  <div >
    <HomeHeader></HomeHeader>
    <HomeSwiper></HomeSwiper>
    <Icons></Icons>
  </div>
</template>

<script>
  import HomeHeader from './pages/Header'
  import HomeSwiper from './pages/Swiper'
  import Icons from './pages/Icons'

  export default {
    name: "Home",
    components: {
      HomeHeader,
      HomeSwiper,
      Icons
    }
  }
</script>

<style scoped>

</style>
