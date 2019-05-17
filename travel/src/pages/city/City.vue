<template>
  <div>
    <city-header></city-header>
    <city-search :cities="cities"></city-search>
    <city-list :letter="letter" :cities="cities" :hot="hotCities"></city-list>
    <city-aphabet
      :cities="cities"
      @change="handleHandleChange"
    ></city-aphabet>
  </div>
</template>

<script>

import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAphabet from './components/Aphabet'
import axios from 'axios'

export default {
  name: "City",
  components: {CityHeader,CitySearch,CityList,CityAphabet},
  data(){
    return {
      cities: [],
      hotCities: [],
      letter: null
    }
  },
  mounted(){
    this.getCityInfo()
  },
  methods:{
    getCityInfo(){
      axios.get('/api/city.json')
        .then(this.handleGetCityInfoSucc)
    },
    handleGetCityInfoSucc(res){
      res = res.data;
      if (res.ret && res.data){
        const data = res.data;
        this.cities = data.cities;
        this.hotCities = data.hotCities;
      }
    },
    handleHandleChange(letter){
      // console.log(letter);
      this.letter=letter
    }
  }
}
</script>

<style lang="stylus" scoped>

</style>
