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

  <ComposantUn>
    <template vslot:kiwi>
      <header> kiwi </header>
    </template>
    <template vslot:cerise>
      <h2> cerise </h2>
    </template>
    <template vslot:fraise>
      <button> fraise </button> <!-- comme fraise est en premier dans composant un -->
    </template>
  </ComposantUn>

  </div>
</template>

<script>
import slotbutton from "./slot-button.vue";
import ComposantUn from "./ComposantUn";

export default {
  name: "Exercise4",

  components: {slotbutton, ComposantUn},
};
</script>

<style>
/* @import '../../theme.styl'; */

.exercise-4 {
  color: $grey;
}
</style>
