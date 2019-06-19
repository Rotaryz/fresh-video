<template>
  <div class="video-page">
    <div class="container">
      <img src="./video-bc@2x.png" alt="" class="page-bc">
      <div class="video-container">
        <video v-if="showIdx == 1" src="./1.mp4" class="video" controls preload></video>
        <video v-if="showIdx == 2" src="2.MOV" class="video" controls preload></video>
      </div>
      <div class="tabs">
        <div class="tab-item hand" @click="changeVideo(1)">商城系统1</div>
        <div class="tab-item hand" @click="changeVideo(2)">商城系统2</div>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  const PAGE_NAME = 'VIDEO'

  export default {
    name: PAGE_NAME,
    page() {
      return {
        title: '赞播优鲜'
      }
    },
    data() {
      return {
        showIdx: 1
      }
    },
    methods: {
      changeVideo(idx) {
        this.showIdx = +idx
      }
    }
  }
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  @import "~@design"

  .video-page
    width: 100vw
    min-width: 1500px
    min-height: 100vh
    display: flex
    align-items: center
    .container
      width: 100%
      height: 0
      padding-top: 56.25%
      position: relative
      .page-bc
        position: absolute
        left: 0
        top: 0
        width: 100%
        height: 100%
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
      .tabs
        position: absolute
        left: 50px
        bottom: 100px
        display: flex
        .tab-item
          width: 100px
          height: 30px
          background: white
          margin-right: 20px

  .test
    height: 10px
</style>
