<template>
  <div class="exercise-2">
    <!-- utilisateur on l'appelle comme sur ligne 22, la meme clé, on met users obliger -->
    <div class="card" v-for="utilisateur in tableauUsers" :key="utilisateur.id">
      <!-- on rend la classe du nom de l'utilsateur dynamique pour changer de couleur le nom quand il est premium -->
      <p :class="{premium: utilisateur.premium}"> ✨{{ fullName(utilisateur) }} </p>
      <!-- autre facon de faire  -->
      <p v-if="utilisateur.premium" class="premium"> ✨ PREMIUM </p>

      <!-- y faut rajouter du coup image: lien dans data.js -->
       <!-- <img :src="utilisateur.image" alt="image aléatoire"> -->

       <!-- autre possibilité -->
       <img :src="urlImage +utilisateur.id" alt="autre image aléatoire">

      <p> {{ utilisateur.email }} </p>
      <p> {{ utilisateur.password }}</p>

      <!-- pour se premiumiumise -->
      <button @click="utilisateur.premium = !utilisateur.premium" >
        <!-- comme si on avait marqué === true  -->
       <span v-if="!utilisateur.premium "> je premiumiumise </span>
       <!-- comme si on avait marqué === true  -->
       <span v-if="utilisateur.premium "> je depremiumiumise </span>
      </button>

      <!-- custom event -->
      <button @click="supprimer(utilisateur)" type="button" name="button">
          supprimer
      </button>
    </div>
  </div>
</template>

<script>
//on commence par importer le fichier data.js et users est une const dans data.js voila pourquoi

  import { users } from "./data";

  export default {
    name: "Exercise2",

    //pour qu'on puisse s'en servir en dehors des balises
    data() {
      return {
        //la clé et la valeur
        tableauUsers: users,
        urlImage: "http://lorempixel.com/400/200/animals/",
      };
    },
    //pour afficher le nom en complet avec une variable
    methods:{
      fullName(utilisateur){
        return utilisateur.firstname + " " + utilisateur.lastname;
      },

      //envoyer des données dans le payload pour que les données sois récupéré plus haut  
      supprimer(membre){
        this.$emit("bannissement", membre)
      },
    },
  };
</script>

<style lang="stylus" scoped>
  @import '../../theme.styl';

  .exercise-2 {
    color: $grey;
    display: flex;
    flex-direction : column;
    align-items: center;
  }

  .card {

    background-color: #d1e4fb;;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    align-content: center;
    margin: 1vh 2vw;
  }

  .card .name {
    font-weight: bold;
  }

  .notPremium {
    display: none;
  }

  .premium{
    color: pink;
  }
</style>
