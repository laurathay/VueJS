<template lang="html">
  <div class="client">
    <button @click"=goToClient(2)" name="button">
      Check mon client
    </button>

  </div>
</template>

<script>
export default {
  name:"Client",

  methods:{
    goToClient(client){
      this.$router.push({ path: "/users", params:{ id: identifiant}});
    },
  },
}
</script>

<style lang="css" scoped>
</style>
