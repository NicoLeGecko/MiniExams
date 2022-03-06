<script>
    export default {
        props: [
            'number',
            'title'
        ]
    }
</script>

<template>
    <div class="questionHeader">
        <p class="questionNumber">{{ number }}</p>
        <p class="questionTitle">{{ title }}</p>
    </div>
</template>

<style>

.questionHeader {
  background-color: rgb(31, 56, 129);
  display: flex;
}

.questionNumber {
  margin: 1em 1em
}

.questionTitle {
  margin: 1em 1em
}

</style>