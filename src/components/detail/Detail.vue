<template>
  <div>
    <DetailBanner
      :sightName="sightName"
      :bannerImg="bannerImg"
      :gallaryImgs="gallaryImgs"
    ></DetailBanner>
    <detail-header></detail-header>

    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
  import DetailBanner from './components/Banner'
  import DetailHeader from './components/Header'
  import DetailList from './components/List'

  import axios from "axios";

  export default {
    name: "Detail",
    components: {
      DetailBanner,
      DetailHeader,
      DetailList

    }, data() {
      return {
        sightName: '',
        bannerImg: '',
        gallaryImgs: [],
        list: []
      }
    },
    methods: {
      getDetailInfo() {
        axios.get('https://www.easy-mock.com/mock/5d331f2f70b5c8763d05c93d/WhereWeGo/detail',
          {
            params:
              {
                id: this.$route.params.id
              }
          }
        ).then(response => {
          if (response.data.ret && response.data.data) {
            this.sightName = response.data.data.sightName;
            this.bannerImg = response.data.data.bannerImg;
            this.gallaryImgs = response.data.data.gallaryImgs;
            this.list = response.data.data.gallaryImgs;
            console.log(this.bannerImg)
          }
        });
      }
    }, mounted() {
      this.getDetailInfo()
    }
  }
</script>

<style scoped lang="stylus">
  .content
    height: 50rem
</style>
