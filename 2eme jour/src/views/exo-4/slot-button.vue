<template>
  <div class="slot-button">

  <h1> <slot name="title"/> </h1>

    <button type="submit" @click="patate()">
    <!-- <button type="button" onclick="alert('Vous avez bien cliqué ici')"> -->
    <slot> Default </slot>
      <slot name="button"/>

    </button>
  <p> <slot name="paragraph"/> </p>
  </div>

</template>

<script>
export default {
  name: "slotbutton",

  methods: {
    patate() {
      alert ("hey you");
    }
  },
};
</script>

<style lang="css" scoped>
  .slot-button{
    color: pink;
    background-color: yellow;
    border-color: inherit;
    border-style: solid;
    padding: 5px 5px;
  }
</style>
