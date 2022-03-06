<script setup>
import QuestionCard from './components/QuestionCard.vue';
</script>

<template>
  <header>
    <div id="examContext">
      <h1>My mini-exam</h1>
    </div>
  </header>

  <main>
    <QuestionCard />
  </main>
</template>

<style>
@import './assets/miniExamsBase.css';

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
}

header {
}

</style>
