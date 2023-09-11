<template>
  <div v-show="drawChart">
    hello
    {{ chart }}
  </div>
</template>
<script>
import Chart from 'chart.js/auto';
import sourceData from '../data.json';
export default {
  name: 'DashboardChart',
  props: {
    chart : HTMLCanvasElement,
  },
  data() {
    return {
      expenses: sourceData.dashboard[0].expenses,
    };
  },

  computed: {
    drawChart() {
      let ctx = this.chart.getContext('2d');
      let barChart = new Chart(ctx, {
        type: 'bar',
        data: {
          labels: ['health', 'shopping', 'traveling', 'food'],
          datasets: [
            {
              label: 'Expenses',
              data: [this.expenses],
            },
          ],
          backgroundColor: [],
        },
        options: {
          title: {
            display: true,
            text: 'Your Expenses this month',
          },
        },
      });
      return true;
    },
  },
};
</script>
