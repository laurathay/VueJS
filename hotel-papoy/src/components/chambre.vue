<template lang="html">
  <div class="chambre">

    <h1>Chambre n°{{number}}</h1>
      <p>Prix: {{price}}€</p>
      <p>Nombre de lits: {{numberOfBed}}</p>
      <p v-if="hasBathroom">Salle de bain privative 🛁</p>
      <p v-if="hasBalcon">Balcon privatif 🏔</p>
      <p v-if="hasAirConditionning">Air conditionné 🌬</p>
      <p v-if="KingSizeBed">Lit KingSize 🛏</p>


  </div>
</template>

<script>
export default {
  name: chambre,

  props: {
    number: {
            type: Number,
            required: true,
        },
        price: {
            type: Number,
            required: true,
        },
        numberOfBed: {
            type: Number,
            required: true,
        },
        hasBathrooom: {
            type: Boolean,
            default: true,
        },
        hasBalcon: {
            type: Boolean,
            default: false,
        },
        hasAirConditionning: {
            type: Boolean,
            default: false,
        },
        IsDisponible: {
            type: Boolean,
            required: true,
        },
        KingSizeBed: {
            type: Boolean,
            default: false,
        },
  },
}
</script>

<style lang="scss" scoped>

.Room {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

</style>
