<template>
  <div class="header-swiper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <!-- slides -->
      <swiper-slide v-for="swi in list" :key="swi.id">
        <img :src="swi.url" alt="加载失败">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
  import 'swiper/dist/css/swiper.css'////这里注意具体看使用的版本是否需要引入样式，以及具体位置。
  import {swiper, swiperSlide} from 'vue-awesome-swiper'

  export default {
    name: "Swiper",
    props:{
      list:Array
    },

    data() {
      return {
        // swiperList: [
          // {
          //   id: "01",
          //   url: 'https://h-des-activity-fecp.qunarzz.com/h_des_activity_fe_h_des_activity_fe/973dc1ae0da73a58410186df08ff25cb.jpg'
          // }, {
          //   id: "02",
          //   url: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/a685001bbf5e77a203ff8815e953efbe.jpg_945x288_52b6ec01.jpg'
          // }, {
          //   id: "03",
          //   url: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/0677c297245b8a489ee12ab9b165c928.jpg_945x288_600cb364.jpg'
          // }
        // ],
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
      swiper() {
        return this.$refs.mySwiper.swiper
      },
      mounted() {
        // current swiper instance
        // 然后你就可以使用当前上下文内的swiper对象去做你想做的事了
        console.log('this is current swiper instance object', this.swiper);
        this.swiper.slideTo(3, 1000, false)
      },
      showSwiper(){
        return this.list;
      }
    }
  }
</script>

<style scoped>
  .header-swiper {
    background: #ccc;
    height: 0;
    padding-bottom: 30%;
  }

  .header-swiper img {
    width: 100%;
    height: 100%;

  }

</style>
