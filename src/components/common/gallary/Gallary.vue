<template>
  <div class="container" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper :options="swiperOptions">
        <swiper-slide
          v-for="(item,index) in imgs"
          :key="index"
        >
          <img class="gallary-img" :src="item">
        </swiper-slide>

        <div class="swiper-pagination" slot="pagination"></div>

      </swiper>
    </div>
  </div>
</template>

<script>
  import Swiper from "@/components/home/pages/Swiper";
  import 'swiper/dist/css/swiper.css'////这里注意具体看使用的版本是否需要引入样式，以及具体位置。
  import {swiper, swiperSlide} from 'vue-awesome-swiper'

  export default {
    name: "Grallary",
    props: {
      imgs: Array,
    },
    components: {Swiper},
    data() {
      return {
        swiperOptions: {
          pagination: '.swiper-pagination',
          paginationType: 'fraction',
          observeParents: true,
          observer: true
        }
      }
    },
    components: {
      swiper,
      swiperSlide
    },
    computed: {
      swiper() {
        return this.$refs.mySwiper.swiper
      },
      mounted() {
        // current swiper instance
        // 然后你就可以使用当前上下文内的swiper对象去做你想做的事了
        console.log('this is current swiper instance object', this.swiper);
        this.swiper.slideTo(3, 1000, false)
      },
      showSwiper() {
        return this.list;
      }
    },
    methods: {
      handleGallaryClick() {
        this.$emit('close')
      }
    }
  }
</script>

<style scoped lang="stylus">
  .container
    position: fixed
    left: 0
    right: 0
    bottom: 0
    background: #000
    z-index: 99
    flex-direction: columns
    justify-content: center


</style>
