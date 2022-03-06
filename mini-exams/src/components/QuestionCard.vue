<script setup>
defineProps()
</script>

<template>
  <div class="questionCard">
    <div class="questionHeader">
        <p class="questionNumber">1</p>
        <p class="questionTitle">Triangles</p>
    </div>
    <div class="questionFormulation">
      <p>What is the hypotenuse?</p>
    </div>
    <div class="answerAlternatives">
      <div class="answerAlternative">
        <input type="radio" id="alternative1">
        <label for="alternative1">The longest side of a right triangle</label>
      </div>
      <div class="answerAlternative">
        <input type="radio" id="alternative2">
        <label for="alternative1">The rightest side of a long triangle</label>
      </div>
    </div>
  </div>
</template>

<style scoped>
.questionCard {
  background-color: royalblue;
  padding: 0.3em 0.3em;
  width: 100%;
}

.questionCard:hover {
  padding: 0.4em 0.4em;
  transition: 150ms;
  transition-timing-function: ease-in-out;
}

.questionHeader {
  background-color: rgb(31, 56, 129);
  display: flex;
}

.questionNumber {
  margin: 1em 1em
}

.questionTitle {
  margin: 1em 1em
}

.questionFormulation {
  margin: 0.2em 0.2em;
}

.answerAlternatives {
  display: flex;
  flex-direction: column;
  margin: 0.2em 0.2em;
}

.answerAlternative {
  margin: 0.2em;
}

</style>
