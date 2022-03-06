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
    },
    methods: {
      newCard() {
        this.cards.push({id:this.cards.length+1});
      },
      removeCard(id) {//<-- somehow this does not work as expected
        console.log('removing card number ' + id) 
        console.log('looking at entry ' + this.cards.map(c => c.id).indexOf(id));
        this.cards.splice(id-1, 1);
        this.reorderQuestions();
      },
      reorderQuestions() {//<-- somehow this does not work as expected
        for (let i = 0; i < this.cards.length; i++) {
          const card = this.cards[i];
          card.id = i+1;
        }
      }
    }
  }
</script>

<template>
  <header>
    <div class="examContext">
      <input type="text" v-model="title" placeholder="Name your exam..."/>
    </div>
  </header>

  <main>
    <div class="cards">
      <QuestionCard 
      v-for="card in cards" 
      :key="card.id" 
      :number="card.id"
      :title="card.title"
      :formulation="card.formulation"
      :answerAlternatives="card.answerAlternatives"
      @deleted="removeCard"
      />
    </div>

    <div class="addQuestion">
      <button @click="newCard">Add a new question</button>
    </div>
  </main>
</template>

<style>
@import './assets/miniExamsBase.css';

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.cards {
  width: 200%;
}

.addQuestion {
  margin: 1em;
}

.examContext>input {
  font-size: larger;
}

</style>
