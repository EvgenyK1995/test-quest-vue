<template>
  <div class="graph">

  </div>
</template>

<script>
  export default {
    name: "Graph"
  }
</script>

<style lang="stylus" scoped>
  .graph
    background-color #f6f6f6
    border 1px solid #efefef
    box-sizing border-box
    height 200px
    padding 20px
    width 100%
    @media (min-width 481px)
      border-radius 5px
    @media (min-width 769px)
      justify-content flex-end
      margin-left 5%
      order 5
      width 45%
    @media (min-width 481px) and (max-width 769px)
      margin-top 20px
</style>