<template>
  <div class="video-page">
    <div class="container">
      <img src="./video-bc@2x.png" alt="" class="page-bc">
      <div class="video-container">
        <video src="./1.mp4" class="video" controls></video>
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
      return {}
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

  .test
    height: 10px
</style>
