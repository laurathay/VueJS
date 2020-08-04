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
    };
  },
};
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';

.exercise-2 {
  color: $grey;
}
</style>
