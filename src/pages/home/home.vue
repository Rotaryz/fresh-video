<template>
  <div class="home">
    <div class="container">
      <div class="container-header">
        <div class="head-left">
          <img class="left-img" src="./pic-logo_home@2x.png" alt="">
        </div>
        <div class="head-right">
          <p class="right-big">三大系统使用教程</p>
          <p class="right-gray">THREE SYSTEMS USE TUTORIAL</p>
        </div>
      </div>
      <div class="container-content">
        <div v-for="(item, index) in arr" :key="index" class="content-item">
          <img class="item-icon" :src="item.icon" alt="">
          <div class="item-line"></div>
          <div class="item-txt">{{item.txt}}</div>
          <div class="item-english">{{item.english}}</div>
          <div class="item-button hand" @click="navigateto(item)">
            <p class="button-txt">查看</p>
            <img class="button-icon" src="./icon-play@2x.png" alt="">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  const PAGE_NAME = 'HOME'
  const LIST = [
    {icon: './imgs/icon-mall@2x.png', txt: '商城系统', english: 'MALL SYSTEM', type: 'mall'},
    {icon: './imgs/icon-supplychain@2x.png', txt: '供应链系统', english: 'SUPPLY CHAIN SYSTEM', type: 'supply'},
    {icon: './imgs/icon-data@2x.png', txt: '数据系统', english: 'DATA SYSTEM', type: 'data'}
  ]

  export default {
    name: PAGE_NAME,
    page: {
      title: '赞播优鲜'
    },
    data() {
      return {
        arr: LIST
      }
    },
    methods: {
      navigateto(item) {
        this.$router.push(`/video?type=${item.type}`)
      }
    }
  }
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  @import "~@design"
  .home
    width: 100vw
    min-width: 1200px
    min-height: 100vh
    background: #f8f8f8
    display: flex
    align-items: center
    justify-content: center
    .container
      width: 77.39%
    @media screen and (max-width: 1200px) {
      .container-header {
        height: 43px
        margin-bottom: 27.6px
      }
      .container-header .head-left {
        width: 120px
      }
      .container-header .head-right .right-big {
        font-size: 19px
      }
      .container-header .head-right .right-gray {
        font-size: 12px
      }
      .container-content .content-item {
        padding: 52px 0 58px
      }
      .container-content .content-item:hover {
        top: -12.5px
      }
      .container-content .content-item .item-line{
        width: 50px
        height: 4px
        border-radius: 2px
        margin: 30px 0 24px
      }
      .container-content .content-item .item-icon{
        width: 125px
        height: 125px
      }
      .container-content .content-item .item-txt{
        font-size: 19px
      }
      .container-content .content-item .item-english{
        font-size: 12px
        margin: 12px 0 70px
      }
      .container-content .content-item .item-button{
        width: 125px
        height: 30px
        border-radius: 15px
      }
      .container-content .content-item .item-button .button-txt{
        font-size: 15px
      }
      .container-content .content-item .item-button .button-icon{
        width: 15px
        height: 15px
        margin-left: 4px
      }
    }
    @media screen and (min-width: 1201px) {
      .container-header {
        height: 3.54vw
        margin-bottom: 2.3vw
      }
      .container-header .head-left {
        width: 10vw
      }
      .container-header .head-right .right-big {
        font-size: 1.6vw
      }
      .container-header .head-right .right-gray {
        font-size: 1.04vw
      }
      .container-content .content-item {
        padding: 4.3vw 0 4.8vw
      }
      .container-content .content-item:hover {
        top: -1.04vw
      }
      .container-content .content-item .item-line{
        width: 4.1vw
        height: 0.26vw
        border-radius: 0.13vw
        margin: 2.4vw 0 2vw
      }
      .container-content .content-item .item-icon{
        width: 10.4vw
        height: 10.4vw
      }
      .container-content .content-item .item-txt{
        font-size: 1.6vw
      }
      .container-content .content-item .item-english{
        font-size: 1.04vw
        margin: 1vw 0 5.8vw
      }
      .container-content .content-item .item-button{
        width: 10.4vw
        height: 2.5vw
        border-radius: 1.25vw
      }
      .container-content .content-item .item-button .button-txt{
        font-size: 1.25vw
      }
      .container-content .content-item .item-button .button-icon{
        width: 1.25vw
        height: 1.25vw
        margin-left: 0.3vw
      }
    }
    .container-header
      display: flex
      justify-content: space-between
      .head-left
        .left-img
          width: 100%
          height: auto
      .head-right
        height: 100%
        display: flex
        flex-direction: column
        justify-content: space-between
        .right-big
          text-align: right
          font-family: PingFangSC-Regular
          color: #3F3F3F
        .right-gray
          font-family: DIN-Bold
          color: #CECECE
          letter-spacing: 1px
    .container-content
      width: 100%
      display: flex
      .content-item
        flex: 1
        margin-right: 4.5%
        display: flex
        flex-direction: column
        align-items: center
        background: #FFFFFF
        box-shadow: 0 2px 40px 0 #EDF0FB
        border-radius: 10px
        position: relative
        top: 0
        transition: all .3s
        &:hover
          box-shadow: 0 2px 40px 0 #C9CEDF
        .item-line
          background: #BBF3FB
        .item-txt
          font-family: PingFang-SC-Bold
          color: #637CE5
          letter-spacing: 1px
        .item-english
          opacity: 0.35
          font-family: DIN-Bold
          color: #637CE5
          letter-spacing: 1px
        .item-button
          border: 1px solid #5472F1
          display: flex
          align-items: center
          justify-content: center
          &:hover
            background: #5472F1
            box-shadow: 0 2px 16px 0 #B6C4FC
            .button-txt
              color: white
          .button-txt
            font-family: PingFangSC-Regular
            color: #5472F1
            letter-spacing: 1.2px
        &:last-child
          margin-right: 0

</style>
