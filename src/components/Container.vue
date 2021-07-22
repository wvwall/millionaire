<template>
  <div class="container">
    <Question />
    <Answers />
  </div>
</template>

<script>
import Question from "./Question.vue";
import Answers from "./Answers.vue";
export default {
  name: "Container",
  components: {
    Question,
    Answers,
  },
};
</script>
