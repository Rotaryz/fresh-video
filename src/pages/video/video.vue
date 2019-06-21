<template>
  <div class="video-page">
    <img class="bc-left page-bc" src="./pic-left@2x.png" alt="">
    <img class="bc-right page-bc" src="./pic-right@2x.png" alt="">
    <div class="container">
      <div class="container-bc">
        <img class="bc-img" src="./pic-playbox@2x.png" alt="">
      </div>
      <div class="logo-icon">
        <img class="icon-img" src="./pic-logo_play@2x.png" alt="">
      </div>
      <div class="icon-people">
        <img class="people-img" src="./pic-people@2x.png" alt="">
      </div>
      <div class="video-container">
        <video :src="videoUrl" class="video" controls preload></video>
      </div>
      <div class="list">
        <div v-for="(item, index) in arr" :key="index" class="list-item">
          <p class="item-title">{{item.txt}}</p>
          <div class="item-list">
            <div v-for="(item1, idx) in item.list" :key="idx" :class="{'active' : item1.type === selected}" class="item-txt hand" @click="changeVideo(item1)">{{item1.txt}}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  const PAGE_NAME = 'VIDEO'
  const LIST = [
    {
      type: 'mall',
      txt: '商城系统',
      list: [
        {txt: '业务流程', type: 'mall-1', url: './imgs/1.mp4'},
        {txt: '拓展活动', type: 'mall-2', url: './imgs/2.MOV'},
        {txt: '营销活动', type: 'mall-3', url: './imgs/1.mp4'},
      ]
    },
    {
      type: 'supply',
      txt: '供应链系统',
      list: [
        {txt: '业务流程', type: 'supply-1', url: './imgs/2.MOV'},
        {txt: '数字化', type: 'supply-2', url: './imgs/1.mp4'},
        {txt: '移动化', type: 'supply-3', url: './imgs/2.MOV'},
      ]
    },
    {
      type: 'data',
      txt: '数据系统',
      list: [
        {txt: '数据图谱', type: 'data-1', url: './imgs/1.mp4'},
        {txt: '选品数据', type: 'data-2', url: './imgs/2.MOV'},
        {txt: '社群数据', type: 'data-3', url: './imgs/1.mp4'},
      ]
    }
  ]

  export default {
    name: PAGE_NAME,
    page() {
      return {
        title: '赞播优鲜'
      }
    },
    data() {
      return {
        videoUrl: '',
        selected: 'mall-1',
        arr: LIST
      }
    },
    created() {
      let type = this.$route.query.type || 'mall'
      this.selected = type + '-1'
      let arr = this.arr.filter((item) => {
        return item.type === type
      })
      this.videoUrl = arr[0].list[0].url
    },
    methods: {
      changeVideo(item) {
        this.videoUrl = item.url
        this.selected = item.type
      }
    }
  }
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  @import "~@design"

  .video-page
    width: 100vw
    min-width: 1200px
    min-height: 100vh
    display: flex
    align-items: center
    background: #798DF4
    position: relative
    @media screen and (max-width: 1200px) {
      .bc-left {
        width: 438px
      }
      .bc-right {
        width: 321px
      }
    }
    @media screen and (min-width: 1201px) {
      .bc-left {
        width: 36.51vw
      }
      .bc-right {
        width: 26.77vw
      }
    }
    .page-bc
      position: absolute
      z-index: 10
    .bc-left
      left: 0
      top: 0
    .bc-right
      right: 0
      bottom: 0
    .container
      width: 100%
      height: 0
      padding-top: 56.25%
      position: relative
      z-index: 100
      @media screen and (max-width: 1200px) {
        .logo-icon {
          width: 125px
        }
        .icon-people {
          width: 220px
        }
        .list .list-item {
          margin-right: 50px
        }
        .list .list-item .item-title{
          font-size: 18px
          margin-bottom: 18px
        }
        .list .list-item .item-list .item-txt{
          padding: 7px 12px
          margin-right: 10px
          font-size: 13px
        }
      }
      @media screen and (min-width: 1201px) {
        .logo-icon {
          width: 10.5vw
        }
        .icon-people {
          width: 18.33vw
        }
        .list .list-item {
          margin-right: 4.16vw
        }
        .list .list-item .item-title{
          font-size: 1.56vw
          margin-bottom: 1.56vw
        }
        .list .list-item .item-list .item-txt{
          padding: 0.6vw 1.04vw
          margin-right: 0.8vw
          font-size: 1.14vw
        }
      }
      .container-bc
        position: absolute
        left: 8.75%
        top: 5.37%
        width: 67.13%
        .bc-img
          width: 100%
          height: auto
      .icon-people
        position: absolute
        top: 27.54%
        right: 8.56%
        .people-img
          width: 100%
          height: auto
      .logo-icon
        position: absolute
        top: 6%
        right: 9%
        .icon-img
          width: 100%
          height: auto
      .video-container
        background: black
        position: absolute
        left: 11.04%
        top: 9.44444%
        width: 62.5%
        height: 64.44444%
        overflow: hidden
        .video
          width: 100%
          height: 100%
      .list
        position: absolute
        left: 8.75%
        bottom: 8.6%
        display: flex
        .list-item
          .item-title
            font-family: PingFang-SC-Bold
            color: white
          .item-list
            display: flex
            .item-txt
              border: 1px solid white
              border-radius: 6px
              font-family: PingFangSC-Regular
              color: white
              &.active
                background: white
                color: #515FAD
              &:hover
                background: white
                color: #515FAD
              &:last-child
                margin-right: 0
</style>
