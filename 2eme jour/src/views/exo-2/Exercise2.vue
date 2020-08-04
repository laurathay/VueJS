<template>
  <div class="exercise-2">
    <div class="card" v-for="(utilisateur, index) in users" :key="index">
      <!-- <label v-model="lastname"> -->
         {{ fullname }}
      <p>{{utilisateur.email}}</p>
      <p>{{utilisateur.password}}</p>

      <!-- pour le binding pour indiquer que l'utilisateur est premium en use classes dynamiques -->
      <p :class="{'notPremium' : !utilisateur.premium}">Compte Premium ✨</p>
      <img :src="utilisateur.image" alt="">

      <!-- Ajouter un bouton permettant de rendre premium ou non les utilisateurs  -->
      <button v-if="!utilsateur.premium" type="button" name="button" :class="{'active': utilisateur.premium}" @click="utilisateur.premium = !utilisateur.premium">
        Devenir Premium
      </button>

      <button v-if="utilsateur.premium" type="button" name="button" :class="{'active': utilisateur.premium}" @click="utilisateur.premium = !utilisateur.premium" >
        Laisse tomber je suis déjà cool
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
        users: users,
        firstname:"" ,
        lastname:"" ,

        notPremium: true,
      };
    },

    computed:{
      fullName(){
        return`${this.firstname} + ${this.lastname}`;
      },
    },

    methods:{
      goPremium(){
        this.notPremium : false,

      }
    }
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
    width: 300px;
    height: 200px;
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
</style>
