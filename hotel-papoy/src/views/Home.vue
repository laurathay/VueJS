<template>
  <div class="home">
    <!-- le nom de ma props avec sa variable -->
    <client :firstname="prenom" :lastname="nom" :address="adresse" :email="courriel"></client>

  </div>
</template>

<script>
// @ is an alias to /src
import client from '@/components/client.vue'

export default {
  name: 'Home',

  components: {
    client
  },

  data(){
    return {
        prenom: "Boo",
        nom: "BOO",
        adresse:"234 rue des boulets",
        courriel: "jaipasdemail@email.com"
    };
  },
};

</script>
