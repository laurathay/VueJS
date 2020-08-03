template>
  <div class="exercise-1">
    <!-- ## Templating -->
    <h1>Bienvenue, {{ firstname + " " + lastname}} !</h1>
    <h1>Bienvenue, {{ firstname }} {{ lastname }} !</h1>
    <!-- ## Data Binding -->
    <label for="">Mon animal totem est : {{animalTotem}}</label><br>
    <input type="text" v-model="animalTotem"/><br><br>
    <!--## Conditionnal Templating-->
    <p v-if="age && age >= 0">J'ai {{age}} an(s) et je suis née en {{2020 - age}}</p>
    <input type="number" v-model="age"/>
    <!-- parseInt(variable) string > int ou variable.toString() int > string -->
    <p v-if="parseInt(age) > 18">Youpi ! Je peux conduire !</p>
    <p v-else-if="parseInt(age) === 18">C'est le grand jour, je passe mon permis.</p>
    <p v-else-if="parseInt(age) < 18">Je peux passer mon permis dans {{18 - age}} année(s)</p>
  </div>
</template>
<script>
export default {
  name: "Exercise1",
  data() {
    return{
      firstname: "Anne",
      lastname: "Trotreau",
      animalTotem: "",
      age: ""
    }
  }
};
</script>
