<template>
  <div class="exercise-2"></div>
  {{ users }}
</template>

<script>
import{ users } from "./data";

export default {
  name: "Exercise2",

  data(){
    return{
        users:users,
        notPremium; true,
        firstname:" ",
        lastname:" ",
    };
  },

  computed:{
    fullName(){
      return`${this.firstname} ${this.lastname}`;
    },
  },
};
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';

.exercise-2 {
  color: $grey;
}
</style>
