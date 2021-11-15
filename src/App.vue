<template>
  <TopBar @save="save" />
  <div class="content">
    <h3>DATA</h3>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt
    </p>
    <div class="row">
      <Table  v-if="this.Participations.length > 0" :Participations="Participations" />
      <Charts :info="Participations" />
    </div>
  </div>
</template>

<script>
import TopBar from './components/TopBar.vue'
import Table from './components/Table.vue'
import Charts from './components/Charts.vue'

export default {
  name: 'App',
  components: {
    TopBar, 
    Table,
    Charts
  }, 
  data(){
    return {
      Participations: [],
    }
  },
  methods:{
    save(newParticipation){
      this.Participations.push(newParticipation);
    }
  }
}
</script>

<style lang="scss">
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.content{
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  h3{
    margin: .3rem;
    color: rgb(69,85,90);
    font-size: 1.6rem;
  }
  p{
    color: rgb(120,131,134);
    font-size: 700;
  }
  .row{
    margin-top: 2rem;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
</style>
