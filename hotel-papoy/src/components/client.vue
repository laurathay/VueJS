<template lang="html">
  <div class="client">

    <h1> {{fullName}}</h1>
    <h2> {{ address }}</h2>
    <p> {{ email }} </p>

  </div>
</template>

<script>
export default {
  name: 'client',

  props: {
    firstname: {
      type: String,
      default:"",
      required: true,
    },
    lastname: {
      type: String,
      default:"",
      required: true,
    },
    address: {
      type: String,
      default:"",
      required: true,
    },
    email:{
      type: String,
      required: true,
    },
  },

  computed: {
    fullName(){
      //ne pas oublier les this dans le script avec le `${} 
      return `${this.firstname} ${this.lastname}`
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
