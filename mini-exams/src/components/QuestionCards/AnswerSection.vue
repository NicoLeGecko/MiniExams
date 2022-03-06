<script>
import AnswerAlternative from './AnswerAlternative.vue' 
    export default {
        components: {
            AnswerAlternative
        },
        data() {
            return {
                newAlternative: '',
                answers: {
                    alternatives: [],
                    add(text) {
                        this.alternatives.push({ id:this.alternatives.length+1, text:text });
                    },
                    remove(altId) {
                        const index = this.alternatives.map(a => a.id).indexOf(altId);
                        if (index > -1) {
                            this.alternatives.splice(index, 1);
                        }
                    }
                },
                selectedAnswers: []
            }
        },
        methods: {
            onSelected(isSelected, id) {
                if (!isSelected){
                    const index = this.selectedAnswers.indexOf(id);
                    this.selectedAnswers.splice(index, 1);
                } else if (!this.selectedAnswers.includes(id)) {
                   this.selectedAnswers.push(id);
                }
            },
            onRemoved(id) {
                this.onSelected(false, id);
                this.answers.remove(id);
            },
            addNewAlternative() {
                this.answers.add(this.newAlternative);
            }
        }
    }
</script>

<template>
    <div class="answerAlternatives">
      <AnswerAlternative 
        v-for="alternative in answers.alternatives"
        :key="alternative.id"
        :answerId="alternative.id"
        :answerText="alternative.text"
        @selected="onSelected"
        @deleted="onRemoved"
        />
    </div>

    <form class="newAnswerForm" @submit.prevent="addNewAlternative">
        <input class="newAnswer" id="newAlternative" type="text" v-model.trim="newAlternative" 
            placeholder="Enter a new answer alternative..." />
        <input type="submit" value="Add" v-bind:disabled="!this.newAlternative"/>
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