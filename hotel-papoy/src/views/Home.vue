<template>
  <div class="home">
    <!-- le nom de ma props avec sa variable -->
    <client :firstname="prenom" :lastname="nom" :address="adresse" :email="courriel"></client>
    <p> Numéro de réservation et chambre </p>
    <resa :numeroResa="254" :numeroChambre="12" :dateEntree="12/09" :dateSortie="24/09"> </resa>
    <chambre :number="numero" :price="prix" :numberOfBed="nombreDeLit" hasBathroom hasBalcon hasAirConditionning KingSizeBed />

  </div>
</template>

<script>
// @ is an alias to /src
import client from '@/components/client.vue'
import chambre from '@/components/chambre.vue'
import resa from '@/components/resa.vue';

export default {
  name: 'Home',

  components: {
    client,
    resa,
    chambre
  },

  data(){
    return {
        prenom: "Boo",
        nom: "BOO",
        adresse:"234 rue des boulets",
        courriel: "jaipasdemail@email.com"
        numero: 12,
        prix: 80,
        nombreDeLit: 1,
        hasBathrooom: true,
        hasBalcon: true,
        hasAirConditionning: true,
        KingSizeBed: true,
        numberOfReservation: 1245678,
        entry: "12//09/20",
        departure: "30//09/20",
        numberOfRoom: 12,
        idClient: 28743,
    };
  },
};

</script>
