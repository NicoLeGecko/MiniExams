<script>
  import QuestionCard from './components/QuestionCards/QuestionCard.vue'

  export default {
    components: {
      QuestionCard
    },
    data() {
      return {
        cards: [
          {
            id: 1, title: 'Triangles', formulation:'What is the hypotenuse?',
            answerAlternatives: [
              { id:1, text: "The longest side of a right triangle"},
              { id:2, text: "The rightest side of a long triangle"},
            ]
          },
          {
            id: 2, title: 'Squares', formulation:'What is the area of a square?',
            answerAlternatives: [
              { id:1, text: "The square of the side length"},
              { id:2, text: "The length of the square side"},
              { id:3, text: "the side of the square length"},
            ]
          }
        ]
      }
    }
  }
</script>

<template>
  <header>
    <div id="examContext">
      <h1>My mini-exam</h1>
    </div>
  </header>

  <main>
      <QuestionCard 
        v-for="card in cards" 
        :key="card.id" 
        :number="card.id"
        :title="card.title"
        :formulation="card.formulation"
        :answerAlternatives="card.answerAlternatives"
        />
  </main>
</template>

<style>
@import './assets/miniExamsBase.css';

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
}

</style>
