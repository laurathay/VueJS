<template>
  <div class="exercise-5">
    <!-- grace a data on récupère le tout -->
    <div> {{restaurants}} </div>

    <!-- on créé le bouton pour afficher les restaurant au clique qu'on appelle avec la méthode -->
    <button @click="getRestaurants()"> Afficher les restaurants </button>

    <!-- on filtre/ sélectionne les données qu'on veut avec v for dans un tableau avec une clé  -->
    <div class="" v-for="restaurant in restaurants" :key="restaurant.id">

      <!-- pour afficher les données on met les {{ }} selon ce qui est affiché dans l'API -->
      <p>{{restaurant.nom}}</p>
      <p>{{restaurant.type}}</p>
      <p>{{restaurant.adresse}}</p>
      <!-- pour afficher l'image ne pas oublier :src pour dynamiser le parametre-->
      <img :src="restaurant.image" alt="">

    </div>


  </div>
</template>

<script>
export default {
  name: "Exercise5",

    data(){
      return{
      //on met la data dans une boite vide = restaurants
      restaurants: null,
    }
  },

  methods:{
    getRestaurants(){
      // on définit axios
      const axios = require('axios');
      //on met l'adresse de notre API qu'on veut récupérer format json
      axios.get('https://restop-toulouse.herokuapp.com/restos')
      //on ordonne les données en les mettant dans une petite boite data qui va etre rempli de notre get
      // sachant que le nom du tableau de l'adresse s'appelle data c'est pour ca qu'on a mis data a la fin de response
      .then(response => (this.restaurants = response.data))
    }
  },
};
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';

.exercise-5 {
  color: $grey;
}
</style>
