<template>
  <div>
    <CityHeader></CityHeader>
    <CitySearch></CitySearch>
    <CityList
      :cities="cities"
      :hot="hotCities"
      :letter="letter"
    ></CityList>
    <CityAlphabet
      :cities="cities"
      @change="handleLetterChange"
    ></CityAlphabet>
  </div>
</template>

<script>
  import axios from 'axios'
  import CityHeader from './components/Header'
  import CitySearch from './components/Search'
  import CityList from './components/List'
  import CityAlphabet from './components/Alphabet'

  export default {
    name: "City",
    components: {
      CityHeader,
      CitySearch,
      CityList,
      CityAlphabet
    },
    data() {
      return {
        cities: {},
        hotCities: [],
        letter: ''
      }
    },
    created() {
      this.getCityInfo();
    },
    methods: {
      getCityInfo() {
        axios.get('https://www.easy-mock.com/mock/5d331f2f70b5c8763d05c93d/WhereWeGo/city')
          .then(response => {
            // console.log(response);
            if (response.data) {
              this.cities = response.data.data.cities;
              this.hotCities = response.data.data.hotCities;
              console.log(this.cities)
            }
          });
      },
      handleLetterChange(letter) {
        this.letter = letter;
        console.log(letter);
      }
    }
  }
</script>

<style scoped>

</style>
