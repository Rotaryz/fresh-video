<template>
  <div class="home">
    <div class="container">

    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  const PAGE_NAME = 'HOME'

  export default {
    name: PAGE_NAME,
    page: {
      title: '赞播优鲜'
    }
  }
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  @import "~@design"
  .home
    width: 100vw
    min-height: 100vh
    background: #ddd
    display: flex
    align-items: center
    justify-content: center
    .container
      min-width: 1500px
      height: 500px
      background: white
</style>
