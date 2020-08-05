<template>
  <div class="exercise-3">

    <Bouton :hasError="true" :error="Oopsi" :title="name"/>
    <Bouton :title="name2" green/>
    
  </div>
</template>

<script>
//là on importe
import Bouton from "./bouton.vue";

export default {
  name: "Exercise3",

  //on le déclare
  components: { Bouton },
  data() {
        return {
          name: "Un joli bouton",
          name2: "un autre joli bouton",
          error: "voici une erreur",
        }
      }

    };
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';

.exercise-3 {
  color: $grey;
}
</style>
