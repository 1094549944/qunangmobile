<template>
  <div>
    <home-header class="header"></home-header>
    <home-swiper :list="swiperList"
                 class="swiper-banner"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
    <weekend :list="weekendList"></weekend>
  </div>
</template>

<script>
import HomeHeader from './components/header'
import HomeSwiper from './Swiper.vue'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import Weekend from './components/Weekend'
import axios from 'axios'
import { mapState } from 'vuex'
export default {
  name: 'Home',
  data () {
    return {
      latCity: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    Weekend
  },
  computed: {
    ...mapState(['city'])
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json?city=' + this.city).then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.lastCity = this.city
    this.getHomeInfo()
  },
  activated () {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city
      this.getHomeInfo()
    }
  }
}
</script>
<style lang="stylus" scoped>
.header
  position fixed
  top 0
  left 0
  right 0
  z-index 99

.swiper-banner
  padding-top 0.86rem
</style>
