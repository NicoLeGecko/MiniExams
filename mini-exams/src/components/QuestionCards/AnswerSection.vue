<script>
import AnswerAlternative from './AnswerAlternative.vue' 
    export default {
        props: [
            'answerAlternatives'
        ],
        components: {
            AnswerAlternative
        },
        data() {
            return {
                selectedAnswers: []
            }
        },
        methods: {
            onSelected(isSelected, id) {
                if(isSelected && !this.selectedAnswers.includes(id)) {
                   this.selectedAnswers.push(id)
                } else if (!isSelected && this.selectedAnswers.includes(id)) {
                    const index = this.selectedAnswers.indexOf(id);
                    this.selectedAnswers.splice(index, 1);
                }
            }
        }
    }
</script>

<template>
    <div class="answerAlternatives">
      <AnswerAlternative 
        v-for="alternative in answerAlternatives"
        :key="alternative.id"
        :answerId="alternative.id"
        :answerText="alternative.text"
        @isSelected="onSelected"
        />
    </div>

    <p>Selected answers: {{ selectedAnswers }}</p>
</template>

<style>

.answerAlternatives {
  display: flex;
  flex-direction: column;
  margin: 0.2em 0.2em;
}
</style>