<script>
import AnswerAlternative from './AnswerAlternative.vue'
import QuestionHeader from './QuestionHeader.vue'
import QuestionFormulation from './QuestionFormulation.vue'
import AnswerSection from './AnswerSection.vue'

  export default {
    props: [
      'number',
      ],
    components: {
    AnswerAlternative,
    QuestionHeader,
    QuestionFormulation,
    AnswerSection
}
  }
</script>

<template>
  <div class="questionCard">
    
    <QuestionHeader :number="number"/>
    
    <QuestionFormulation />
    
    <AnswerSection />

  </div>
</template>

<style scoped>
.questionCard {
  background-color: royalblue;
  padding: 0.3em 0.3em;
  width: 100%;
  margin:2em
}

/* .questionCard:hover {
  padding: 0.4em 0.4em;
  transition: 150ms;
  transition-timing-function: ease-in-out;
} */

</style>
