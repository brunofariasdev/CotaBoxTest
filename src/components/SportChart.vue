<script>
import { defineComponent } from 'vue'
import { Doughnut } from 'vue3-chart-v2'

export default defineComponent({
  name: 'SportChart',
  extends: Doughnut,
  props: {
    labels: Array, 
    getData: Array
  },
  data () {
    return {
      state: {
       chartData: {
           labels: this.labels,
            datasets: [
              {
                label: 'Human 1',
                data: this.getData,
                backgroundColor: ["#2c97de","#16ba9a","#ea4b35","#9c56b8","#bdc3c7","#00b8e2","#fe8099","#f08d49","#ff0000"]
              },
              
            ]
        },
        chartOptions: {
          responsive: true
        }
      }
    }
  },
  mounted () {
    this.renderChart(this.state.chartData, this.state.chartOptions);
  }, 
  updated(){
      this.$ForceUpdate()
  }
})
</script>