<template>
  <div class="exercise-5">
    <!-- grace a data on récupère le tout -->
    <div> {{restaurants}} </div>

    <!-- on créé le bouton pour afficher les restaurant au clique qu'on appelle avec la méthode -->
    <button @click="getRestaurants()"> Afficher les restaurants </button>

              <!-- rajouter/modifier/supprimer un resto -->
              <h2>Ajouter un restaurant</h2>

                <form>
                    <label for="">nom</label>
                    <input type="text" v-model="nom"/>

                    <label for="">type</label>
                    <input type="text" v-model="type"/>

                    <label for="">adresse</label>
                    <input type="text" v-model="adresse"/>

                    <label for="">telephone</label>
                    <input type="number" v-model="telephone"/>

                    <label for="">plats</label>
                    <input type="text" v-model="plats"/>

                    <button type="button" @click="postRestaurant()">Envoyer</button>
                </form>

                <p v-if="success">Le restaurant a bien été enregistré</p>


    <!-- on filtre/ sélectionne les données qu'on veut avec v for dans un tableau avec une clé  -->
    <!-- <div class="" v-for="restaurant in restaurants" :key="restaurant.id"> -->

      <!-- pour afficher les données on met les {{ }} selon ce qui est affiché dans l'API -->
      <!-- <p>{{restaurant.nom}}</p>
      <p>{{restaurant.type}}</p>
      <p>{{restaurant.adresse}}</p> -->
      <!-- pour afficher l'image ne pas oublier :src pour dynamiser le parametre-->
      <!-- <img :src="restaurant.image" alt=""> -->

    <!-- </div> -->


  </div>
</template>

<script>
export default {
  name: "Exercise5",

    data(){
      return{
      //on met la data dans une boite vide = restaurants
      info: null,
       restaurants: null,
       nom: "utopia",
       type: "tradi",
       plats: "salade",
       adresse: "place",
       telephone: "0987443678",
       success: false,
    }
  },

  methods:{
    // on a rajouter async et await pour eviter then et catch
  //  async getRestaurants(){

      getRestaurants(){
      // on définit axios
      const axios = require('axios');
      //on met l'adresse de notre API qu'on veut récupérer format json
      //axios.get('https://restop-toulouse.herokuapp.com/restos')


      //on change d'api pour la suite de l'exo
     axios.get('http://localhost:3000/restos/')
     //on ordonne les données en les mettant dans une petite boite data qui va etre rempli de notre get
     // sachant que le nom du tableau de l'adresse s'appelle data c'est pour ca qu'on a mis data a la fin de response
     .then(response => (this.restaurants = response.data))


    //  .then(response =>(this.restaurants = response.data))
    //},
      //comme on utilise async await il faut la traiter :
    //   try{
    //     const restosListe = await axios.get("http://localhost:3000");
    //     this.listeRestaurant = this.restosListe.data;
    //
    //   } catch (err){
    //     console.log(err);
    //   };
    // },

      //on ordonne les données en les mettant dans une petite boite data qui va etre rempli de notre get
      // sachant que le nom du tableau de l'adresse s'appelle data c'est pour ca qu'on a mis data a la fin de response
      // .then(response => (this.restaurants = response.data))
  //   }
      },

      postRestaurant() {
        const axios = require('axios');
        axios.post(`http://localhost:3000/restos/`, {
            nom: this.nom,
            type: this.type,
            adresse: this.adresse,
            telephone: this.telephone,
            plats: this.plats,
        })
        .then(() => {
          this.nom = "";
          this.type = "";
          this.adresse = "";
          this.telephone = "";
          this.plats = "";
          this.success = true;
        })
        .catch((err) => {
          console.log(err);
        })
      },

      // putRestaurant() {
      //     const axios = require('axios');
      //     axios.put(`http://localhost:3000/restos/6`, {
      //         name: this.name,
      //         type: this.type,
      //         adresse: this.adresse,
      //         telephone: this.telephone,
      //         plats: this.plats,
      //     })
      //     .then((res) => {
      //       console.log(res);
      //   })
      //   .catch((err) => {
      //     console.log(err);
      //   })
      // },

      // deleteRestaurant() {
      //     const axios = require('axios');
      //
      //     axios.delete('http://localhost:3000/restos/6')
      //     .then((res) => {
      //       console.log(res);
      //   })
      //   .catch((err) => {
      //     console.log(err);
      //   })
      // },
    },

    //  mounted () {
    //  this.getRestaurants();
    // }
  }
  </script>

<style lang="stylus" scoped>
@import '../../theme.styl';

.exercise-5 {
  color: $grey;
}

.exercise-5 input, label{
  display: flex;
}

input{
  border-top : white solid;
  border-right: white solid;
  border-left : white solid;
  border-bottom : black 1px solid;
  margin : 5px 5px;
}

form{
  margin-left:25em;
}

button{
  color: pink;
  padding: 10px 10px;
  background-color: yellow;
  border: white solid;
  border-radius: 20%;
}
</style>
