<script>
  export default {
    props: [
      'answerId',
      'answerText'
      ]    
  }
</script>

<template>
  <div class="answerAlternative">
    <input type="radio" id="alternative{{ answerId }}">
    <label for="alternative{{ answerId }}">{{ answerText }}</label>
  </div>
</template>

<style scoped>

.answerAlternative {
  margin: 0.2em;
}

</style>
