<template>
  <div class="graph">
    <canvas id="myChart"></canvas>
  </div>
</template>

<script>
  import Chart from 'chart.js';

  export default {
    name: "Graph",
    mounted() {

      let ctx = document.getElementById('myChart').getContext('2d');
      let myChart = new Chart(ctx, {
        type: 'bar',
        data: {
          labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
          datasets: [{
            label: '# of Votes',
            data: [12, 19, 3, 5, 2, 3],
            backgroundColor: [
              'rgba(255, 99, 132, 0.2)',
              'rgba(54, 162, 235, 0.2)',
              'rgba(255, 206, 86, 0.2)',
              'rgba(75, 192, 192, 0.2)',
              'rgba(153, 102, 255, 0.2)',
              'rgba(255, 159, 64, 0.2)'
            ],
            borderColor: [
              'rgba(255, 99, 132, 1)',
              'rgba(54, 162, 235, 1)',
              'rgba(255, 206, 86, 1)',
              'rgba(75, 192, 192, 1)',
              'rgba(153, 102, 255, 1)',
              'rgba(255, 159, 64, 1)'
            ],
            borderWidth: 1
          }]
        },
        options: {
          scales: {
            yAxes: [{
              ticks: {
                beginAtZero: true
              }
            }]
          }
        }
      });
    }
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