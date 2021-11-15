<template>
<div class="container">
  <SportChart :labels="getLabels" :getData="getData" />
</div>
</template>

<script>
import { defineComponent } from 'vue'
import SportChart from './SportChart.vue'

export default defineComponent({
  name: 'App',
  props: {
    info: Array,
  },
  components: {
    SportChart
  },
  data(){
      return {
          infos: this.info,
          newArray: []
      }
  },
  computed:{
    Data(){
        let newArray = [];
        for(let i = 0; i < this.infos.length; i++){
           newArray.push({label: this.info[i].firstName, data: parseInt( this.info[i].participation)})       }
        return newArray
    }, 
    getLabels(){
        let newArray = [];
        for(let i = 0; i < this.Data.length; i++){
            newArray.push(this.Data[i].label);
        }
        return newArray
    },
    getData(){
        let newArray = [];
        for(let i = 0; i < this.Data.length; i++){
            newArray.push(this.Data[i].data);
        }
        return newArray
    }
  },
})
</script>

<style scoped>
.container{
    display: flex;
    flex-direction: column;
}
</style>