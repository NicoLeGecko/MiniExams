<script>
    export default {
        data() {
            return {
                formulation: ''
            }
        }
    }
</script>

<template>
    <div class="questionFormulation">
        <input type="text" v-model="formulation" 
            placeholder="Formulate a question..."/>
    </div>
</template>

<style>

.questionFormulation {
  margin: 0.2em 0.2em;
}

</style>