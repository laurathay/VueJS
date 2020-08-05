<template>
  <div class="Bouton">
  <!-- la classe dynamique pour faire contour rouge-->
    <button :class="{'RedError' : hasError , 'green' : green}">
       {{title}}
    </button>

    <!-- la classe error pour afficher un texte derreur-->
    <p v-if="hasError">{{error}}</p>

  </div>
</template>

<script>

export default{
  name: 'Bouton',
  //ajout des props
  props: {
      hasError: {
          type: Boolean,
          default: false,
      },
      error: {
          type: String,
          default: "",
      },
      green: {
        type: Boolean,
        default: false,
      },
      title: {
          type: String,
          required: true,
      },
  }
};
</script>


<style lang="stylus" scoped>
@import '../../theme.styl';

.exercise-3 {
  color: $grey;
}

button {
    border-radius: 10px;
    padding: 3vh 3vw;
    border: solid 1px grey;
    color: grey;
}

.RedError {
    border: solid 1px red;
}

.green {
    background-color : green;
    color: #fff;
}

</style>
