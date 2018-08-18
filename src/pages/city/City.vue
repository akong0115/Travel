<template>
  <div>
    <city-header></city-header>
    <city-search :cities="cities"></city-search>
    <city-list :cities="cities" :hotCities="hotCities" :letter="letter"></city-list>
    <dictionary-map :cities="cities" @change="handleChange"></dictionary-map>
  </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import DictionaryMap from './components/DictionaryMap'
import axios from 'axios'

export default {
  name: 'City',
  components: {CityHeader, CitySearch, CityList, DictionaryMap},
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  mounted () {
    this.getCityInfo()
  },
  methods: {
    getCityInfo () {
      axios.get('api/city.json')
        .then(this.getCityInfoSucc)
    },
    getCityInfoSucc (res) {
      console.log(res)
      res = res.data
      if (res.ret && res.data) {
        this.hotCities = res.data.hotCities
        this.cities = res.data.cities
      }
    },
    handleChange (value) {
      this.letter = value
    }
  }
}
</script>

<style lang="stylus" scoped>

</style>
