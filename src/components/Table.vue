<template>
    <table class="table table-striped table-bordered">
            <thead>
                <tr>
                    <th> </th>
                    <th>FirstName</th>
                    <th>LastName</th>
                    <th>Participation</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(Participation , index) in ParticipationList" :key="index">
                    <td>{{index}}</td>
                    <td>{{Participation.firstName}}</td>
                    <td>{{Participation.lastName}}</td>
                    <td>{{Participation.participation}}%</td>
                </tr>
            </tbody>
        </table>
</template>

<script>
export default {
  name: 'Table',
  props: {
    Participations: Array,
  }, 
  data(){
      return {
          ParticipationList: this.Participations
      }
  }
}
</script>
<style scoped>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 35%;
}

td, th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}
</style>