<template>

  <div class="user-list">
      La liste d'utilisateurs est la trouduc
      {{ utilisateurs }}
  </div>

</template>

<script>
//2. Afficher les utilisateurs du fichier `data.js` de cet exercice
import { membres } from "./data.js";

export default {
  name: "UserList",
  //il faut mettre data pour membres
  data() {
    return {
      utilisateurs: membres,
    };
  },
};

</script>

<style lang="css" scoped>
</style>
