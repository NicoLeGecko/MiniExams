<script>
  export default {
    props: [
      'answerId',
      'answerText',
      ],
    emits: [
      'isSelected'
    ]
  }
</script>

<template>
  <div class="answerAlternative">
    <input type="checkbox" 
      :id="'alternative'+answerId"
      @input="this.$emit('isSelected', $event.target.checked, answerId)"/>

    <label :for="'alternative'+answerId">{{ answerText }}</label>

    <p>{{ isSelected }}</p>

  </div>
</template>

<style scoped>

.answerAlternative {
  margin: 0.2em;
}

</style>
