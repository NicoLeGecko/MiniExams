<script>
  export default {
    props: [
      'answerId',
      'answerText',
      ],
    emits: [
      'selected',
      'deleted'
    ]
  }
</script>

<template>
  <div class="answerAlternative">
    <div>
        <input type="checkbox" 
        :id="'alternative'+answerId"
        @input="this.$emit('selected', $event.target.checked, answerId)"/>
      <label :for="'alternative'+answerId">{{ answerText }}</label>
    </div>
    
    <div>
      <button class="removeButton" @click="this.$emit('deleted', answerId)">Remove</button>
    </div>
  </div>
</template>

<style scoped>

.answerAlternative {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin: 0.2em;
}

.removeButton {
  width: fit-content;
}

</style>
