<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list></city-list>
    <city-aphabet></city-aphabet>
  </div>
</template>

<script>

  import CityHeader from './components/Header'
  import CitySearch from './components/Search'
  import CityList from './components/List'
  import CityAphabet from './components/Aphabet'
    export default {
        name: "City",
      components: {CityHeader,CitySearch,CityList,CityAphabet},
    }
</script>

<style lang="stylus" scoped>

</style>
