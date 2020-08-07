<template>
  <!--
  <template v-slot:title>
  </template> -->
  <div class="exercise-4">

  <slotbutton>
    Hey you
  </slotbutton>
  <slotbutton>
    Bye you
  </slotbutton>

  </div>
</template>

<script>
import slotbutton from "./slot-button.vue";

export default {
  name: "Exercise4",

  components: {slotbutton}
};
</script>

<style>
/* @import '../../theme.styl'; */

.exercise-4 {
  color: $grey;
}
</style>
