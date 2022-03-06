<script>
  import QuestionCard from './components/QuestionCards/QuestionCard.vue'

  export default {
    components: {
      QuestionCard
    },
    data() {
      return {
        title: '',
        cards: [
          {
            id: 1
          }
        ]
      }
    }
  }
</script>

<template>
  <header>
    <div class="examContext">
      <input type="text" v-model="title" placeholder="My mini-exam"/>
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

.examContext>input {
  font-size: larger;
}

</style>
