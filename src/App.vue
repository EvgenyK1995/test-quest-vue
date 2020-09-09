<template>
  <div id="app">
    <h1 class="h1">Прогноз продвижения</h1>
    <div class="content">
      <p class="info-block">
        Мы пользуемся только официальными инструментами рекламы, рекомендуемыми самим YouTube, поэтому все приведённые нами просмотры, лайки и комментарии будут настоящими, а подписчики живыми и заинтересованными в тематике Вашего канала
      </p>
      <user-input @get-cost="updateCost"></user-input>
      <output-block :watches="getWatches" :followers="getFollowers"></output-block>
      <graph :data-list="getDataList"></graph>
      <p class="text-hint-block">
        Прогноз подписчиков зависит от Вашего контента. Сделайте его интересным и старайтесь не снижать планку
      </p>
    </div>
  </div>
</template>

<script>
  import UserInput from "./components/UserInput.vue";
  import OutputBlock from "./components/OutputBlock.vue";
  import Graph from "./components/Graph.vue";

  export default {
    name: "App",
    components: { Graph, OutputBlock, UserInput },
    data() {
      return {
        cost: 0,
        watches: 0.5,
        followers: 0.2
      }
    },
    computed: {
      getWatches() {
        return this.cost / this.watches;
      },
      getFollowers() {
        return Math.round(this.getWatches * this.followers);
      },
      getDataList() {
        let data = [];
        for (let i = 0; i < 6; i++){
          data[i] = Math.round(this.getFollowers / (i + 1) * Math.random());
        }
        data[data.length] = this.getFollowers;

        return data;
      }
    },
    methods: {
      updateCost(_cost) {
        this.cost = _cost;
      }
    }
  }
</script>

<style lang="stylus">
  html
  body
    font-family sans-serif
    margin 0
    padding 0

  #app
    box-sizing border-box
    margin 0 auto
    max-width 1000px
    width 100%
    @media (min-width 481px)
      padding 20px

  .content
    @media (min-width 481px) and (max-width 769px)
      display flex
      flex-wrap wrap
    @media (min-width 769px)
      display flex
      height 375px
      flex-direction column
      flex-wrap wrap

  .h1
    font-size 1.5em
    text-align center
    width 100%
    @media (min-width 769px)
      font-size 2em
      margin 30px 0

  .info-block
    box-sizing border-box
    color #aaa
    font-size 14px
    font-weight bold
    line-height 1.5em
    padding 0 20px
    text-align center
    width 100%
    @media (min-width 769px)
      max-width 45%
      order 0
      padding 0
      text-align left

  .text-hint-block
    box-sizing border-box
    color #a7a7a7
    font-size 14px
    margin 0
    padding 20px
    width 100%
    @media (min-width 481px)
      padding 20px 0
    @media (min-width 769px)
      order 2
      width 45%
</style>