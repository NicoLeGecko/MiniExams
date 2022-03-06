<script>
import AnswerAlternative from './AnswerAlternative.vue' 
    export default {
        props: [
            // 'answerAlternatives'
        ],
        components: {
            AnswerAlternative
        },
        data() {
            return {
                newAlternativeText: '',
                answerAlternatives: [],
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
            },
            onSubmit() {
                if (!this.newAlternativeText)
                    return;

                const newAlternativeId = this.answerAlternatives.length + 1;
                this.answerAlternatives.push({ id:newAlternativeId, text:this.newAlternativeText });
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

    <form class="newAnswerForm" @submit.prevent="onSubmit">
        <input class="newAnswer" id="newAlternative" type="text" v-model.trim="newAlternativeText" 
            placeholder="Enter a new answer alternative..." />
        <input type="submit" value="Add" v-bind:disabled="!newAlternativeText"/>
    </form>

    <p>Selected answers: {{ selectedAnswers }}</p>
</template>

<style>

.answerAlternatives {
  display: flex;
  flex-direction: column;
  margin: 0.2em 0.2em;
}

.newAnswerForm {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
}

.newAnswer {
    width: 80%;
}

</style>