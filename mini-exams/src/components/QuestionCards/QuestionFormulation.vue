<script>
    export default {
        props: [
            'formulation'
        ]
    }
</script>

<template>
    <div class="questionFormulation">
        <p>{{ formulation }}</p>
    </div>
</template>

<style>

.questionFormulation {
  margin: 0.2em 0.2em;
}

</style>