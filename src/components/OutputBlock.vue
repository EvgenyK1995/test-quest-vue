<template>
  <div class="output-block">
    <div class="watches">
      <span class="watches_span">+{{ watches }}</span>
      <span>просмотров</span>
    </div>
    <div class="followers">
      <span class="followers_span">+{{ followers }}</span>
      <span>подписчиков</span>
    </div>
  </div>
</template>

<script>
  export default {
    name: "OutputBlock",
    props: [
      'watches',
      'followers'
    ]
  }
</script>

<style lang="stylus" scoped>
  .output-block
    align-items center
    box-sizing border-box
    display flex
    justify-content space-between
    padding 0 20px
    width 100%
    @media (min-width 481px) and (max-width 769px)
      flex-direction column
      padding-right 0
      width 30%
    @media (min-width 769px)
      justify-content flex-end
      order 4
      padding-right 0
      width 50%

    .watches
    .followers
      align-items center
      background-color #ebe1fc
      border-radius 5px
      box-sizing border-box
      color #313133
      display flex
      flex-basis 45%
      flex-direction column
      font-size 14px
      justify-content center
      margin 20px 0
      padding 20px
      width 45%
      @media (min-width 481px) and (max-width 769px)
        flex-basis 100%
        margin 0
        width 100%

      &_span
        font-size 18px
        font-weight bold
    @media (min-width 481px) and (max-width 769px)
      .watches
        margin-bottom 10px
      .followers
        margin-top 10px
    @media (min-width 769px)
      .followers
        margin-left 20px
</style>