<template>
<div>
  <div class="exercise-1">
    <input type="text" v-model="firstname" />
    <input type="text" v-model="lastname" />
  </div>
  <p v-if="firstname || lastname">Bienvenue, {{ firstname }}  {{ lastname }} !</p>
 </div>
</template>

<script>
export default {
  name: 'Exercise1',

  data() {
    return {
      firstname: "",
      lastname: "",
    };
  },
};
</script> 

<style lang="stylus" scoped>
@import '../../theme.styl';

.exercise-1 h1 {
  color: $grey;
}
</style>
