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
                backgroundColor: ["#41B883", "#E46651", "#00D8FF", "#DD1B16"]
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
  
     
  }
})
</script>