<template>
  <div class="user-list">
    <div class="user" v-for="user in utilisateurs" :key="user.id">
      {{ user.firstname }} {{ user.lastname }}
    </div>

    <!-- Ici on utilise une methode pour se déplacer sur une autre page -->
    <button @click="goToEx1">Aller à l'exercice 1</button>

    <!-- Le router link fonctionne comme une balise <a> 
    mais il dirige toujours vers notre application (jamais vers un autre site) -->
    <router-link to="/exo-2">
      <button>Aller à l'exercice 2</button>
    </router-link>
  </div>
</template>

<script>
import { membres } from "./data.js";

export default {
  name: "UserList",
  data() {
    return {
      utilisateurs: membres,
    };
  },
  methods: {
    goToEx1() {
      // L'objet $router nous permet de naviguer sur une autre page grâce au .push
      this.$router.push({ path: "/exo-1" });
    },
  },
};
</script>

<style>
.user {
  width: 100px;
  height: 50px;
  margin: 20px;
  border: solid 1px red;
}
</style>
