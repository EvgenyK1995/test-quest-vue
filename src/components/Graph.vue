<template>
  <div class="graph">
    <canvas id="followersGraph"></canvas>
  </div>
</template>

<script>
  import Chart from 'chart.js';

  export default {
    name: 'Graph',
    props: ['dataList'],
    data() {
      return {
        followersGraph: null
      };
    },
    watch: {
      dataList: function () {
        this.updateGraph();
      }
    },
    mounted() {
      const ctx = document.getElementById('followersGraph').getContext('2d');
      const gradient = ctx.createLinearGradient(100,0,150,200);
      gradient.addColorStop(1,'rgba(142, 86, 233, 0)');
      gradient.addColorStop(0,'rgba(142, 86, 233, 0.31)');

      this.followersGraph = new Chart(ctx, {
        type: 'line',
        data: {
          labels: ['1 день', '2 день', '3 день', '4 день', '5 день', '6 день', '7 день'],
          datasets: [{
            //data: [0,0,0,0,0,0,0],
            backgroundColor: gradient,
            borderColor: '#7045C4',
            borderWidth: 1
          }]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          legend: {
            display: false,
          },
          scales: {
            yAxes: [{
              ticks: {
                beginAtZero: true
              }
            }]
          }
        }
      });
    },
    methods: {
      updateGraph() {
        this.followersGraph.data.datasets.forEach((dataset) => {
          dataset.data.length = 0;
          dataset.data = this.dataList;
        });

        this.followersGraph.update();
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .graph
    border 1px solid #efefef
    box-sizing border-box
    height 200px
    padding 20px
    position relative
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