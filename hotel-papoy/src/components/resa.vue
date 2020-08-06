<template lang="html">
  <div class="resa">

    <h1> Numéro de réservation :{{ numeroResa }}</h1>
    <h2> Numéro de chambre : {{ numeroClient }}</h2>
    <p> Date d'entrée: {{dateEntree}} </p>
    <p> Date de sortie: {{dateSortie}} </p>
  </div>
</template>

<script>
export default {

  name: "resa",

  props: {
    numeroResa: {
      type: Number,
      required: true,
    },
    numeroChambre: {
      type: Number,
      required: true,
    },
    dateEntree: {
      type: String,
      required: true,
    },
    dateSortie: {
      type: String,
      required: true,
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
