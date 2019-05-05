<template>
    <div>
        <CityHeader>city</CityHeader>
        <CitySearch></CitySearch>
        <CityList :cities="cities" :hot="hotCities"></CityList>
        <CityAlphabet :cities="cities"></CityAlphabet>
    </div>
</template>

<script>
    import axios from 'axios'
    import CityHeader from './components/CityHeader'
    import CitySearch from './components/CitySearch'
    import CityList from './components/CityList'
    import CityAlphabet from './components/CityAlphabet'

    export default {
        name: 'City',
        components: {
            CityHeader,
            CitySearch,
            CityList,
            CityAlphabet
        },
        data () {
            return {
                cities: {},
                hotCities: []
            }
        },
        methods: {
            getCityInfo () {
                axios.get('/api/city.json')
                    .then(this.handleGetCityInfoSucc)
            },
            handleGetCityInfoSucc (res) {
                let r = res.data
                // ret 表示数据请求是否成功；布尔值；
                if (r.ret && r.data) {
                    // console.log('r.ret', r.ret)
                    let data = r.data
                    // console.log('data', data)
                    this.cities = data.cities
                    this.hotCities = data.hotCities
                    // console.log('cities', this.cities)
                    // console.log('hotCities', this.hotCities)
                }
            }
        },
        mounted () {
            this.getCityInfo()
        }
    }
</script>

<style scoped>

</style>
