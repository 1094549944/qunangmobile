<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#58930;</span>输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="
                 header-right
                 ">
        {{this.city}}
        <span class="iconfont
                 arrow-icon
                 ">&#58954;</span>
      </div>
    </router-link>

  </div>

</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }

}
</script>

<style scoped lang="stylus">
@import '~styles/varibles'

.header
  line-height 0.86rem
  display flex
  background $bgColor
  color #fff

  .header-left
    width 0.64rem
    float left

    .back-icon
      text-align center
      font-size 0.4rem

  .header-input
    flex 1
    height 0.64rem
    line-height 0.64rem
    margin-top 0.12rem
    margin-left 0.2rem
    padding-left 0.2rem
    background #fff
    border-radius 0.1rem
    color #ccc

    .iconfont
      padding-right 0.2rem

  .header-right
    min-width 1.04rem
    padding 0 0.1rem
    float right
    text-align center
    color #fff

    .arrow-icon
      margin-left -0.04rem
</style>
