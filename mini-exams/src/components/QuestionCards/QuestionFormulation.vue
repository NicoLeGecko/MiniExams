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
        <span class="textarea" role="textbox" contenteditable > {{formulation}} </span>
    </div>
</template>

<style>

.questionFormulation {
  margin: 0.2em 0.2em;
}

.questionFormulation>textarea {
  width: 100%;
  height: fit-content;
}
    
.textarea {
  display: block;
  width: 100%;
  overflow: hidden;
  resize: both;
  min-height: 3em;
  color: honeydew;
}

.textarea:empty::before {
  content: "Formulate a question...";
  color:rgba(240, 255, 240, 0.767);
}

</style>