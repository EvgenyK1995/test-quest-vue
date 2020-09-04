<template>
  <div class="user-input">
    <p>Введите сумму, чтобы увидеть прогноз<br />по подписчикам и просмотрам</p>
    <div class="input-block">
      <label class="input_label" for="input">
        <img class="input_img" src="/src/img/rubl.png" alt="" />
      </label>
      <input type="number" class="input" id="input" />
      <span class="input_span">руб.</span>
    </div>
  </div>
</template>

<script>
  export default {
    name: "UserInput"
  }
</script>

<style lang="stylus" scoped>
  .user-input
    background-color #e2e5ee
    box-sizing border-box
    color #919297
    font-size 0.85em
    font-weight bold
    padding 20px
    width 100%
    @media (min-width 481px)
      border-radius 5px
    @media (min-width 769px)
      order 1
      width 45%
    @media (min-width 481px) and (max-width 769px)
      width 70%

    .input-block
      align-items center
      display flex
      justify-content space-between
      width 100%
      @media (min-width 769px)
        justify-content left

      .input
        border none
        border-radius 5px
        flex-grow 1
        height 30px
        padding-left 10px
        @media (min-width 769px)
          max-width 200px

        &:focus, &:active
          outline none
        &_label
          flex-basis 40px
        &_img
          width 25px
        &_span
          flex-basis 40px
          text-align right
</style>