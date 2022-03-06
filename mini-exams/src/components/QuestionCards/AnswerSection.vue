<script>
import AnswerAlternative from './AnswerAlternative.vue' 
    export default {
        props: [
            'answerAlternatives'
        ],
        components: {
            AnswerAlternative
        }
    }
</script>

<template>
    <div class="answerAlternatives">
      <AnswerAlternative v-for="alternative in answerAlternatives"
          :key="alternative.id"
          :answerId="alternative.id"
          :answerText="alternative.text"/>
    </div>
</template>

<style>

.answerAlternatives {
  display: flex;
  flex-direction: column;
  margin: 0.2em 0.2em;
}
</style>