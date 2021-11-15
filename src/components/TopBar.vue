<template>
  <form class="contain">
    <input type="text" placeholder="First Name" v-model="newParticipation.firstName">
    <input type="text" placeholder="Last Name" v-model="newParticipation.lastName">
    <input type="tel"  placeholder="Participation" v-model="newParticipation.participation">
    <button @click.prevent="save">SEND</button>
  </form>
</template>

<script>
export default {
  name: 'TopBar',
  props: {
    msg: String
  },
  data(){
    return {
      newParticipation: {
        firstName: '',
        lastName: '',
        participation: '',
      }
    }
  }, 
  methods:{
    save(){
      if(this.newParticipation.firstName != '' || this.newParticipation.lastName != '' || this.newParticipation.participation != '' || this.newParticipation.firstName != ' ' || this.newParticipation.lastName != ' ' || this.newParticipation.participation != ' '){
        this.$emit('save', this.newParticipation);
        this.newParticipation = {};
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.contain{
  height: 8rem;
  width: 100%;
  background-color: rgb(0,184,226);
  display: flex;
  align-items: center;
  justify-content: center;
  input{
    border: none;
    width: 15rem;
    margin-left: 1rem;
    height: 3rem;
    border-radius: 4px;
    padding-left: 1rem;
    color: rgb(117, 117, 117);
    font-weight: 500;
  }
  button{
    margin-left: 1rem;
    width: 8rem;
    height: 3rem;
    border-radius: 4px;
    color: white;
    font-weight: bold;
    background: none;
    border: 2px solid white;
    cursor: pointer;
  }
  button:hover{
    background: rgba(255, 255, 255, 0.425);
    transition: .4s;
  }
}
</style>
