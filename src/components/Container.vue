<template>
  <div class="container">
    <Question
      v-for="(quest, index) in questions"
      :key="'domanda' + index"
      :questions="quest.question"
    />
    <div
      class="container-answ"
      v-for="(quest, index) in questions"
      :key="'risposta' + index"
    >
      <Answers
        @check="checkAnswer"
        :class="{ green: correct, red: error }"
        v-for="(date, index) in quest.answers"
        :key="'data' + index"
        :answer="date"
      />
    </div>
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

  data() {
    return {
      correct: null,
      error: null,
      db_questions: [
        {
          question: "In che anno è nato Wall?",
          answers: ["1995", "1997", "1994", "1998"],
          correct: "1995",
        },
        {
          question: "In che anno si svolti gli Europei 2020?",
          answers: ["2021", "2020", "2022", "2019"],
          correct: "2021",
        },
      ],
      questions: [
        {
          question: "In che anno è nato Wall?",
          answers: ["1995", "1997", "1994", "1998"],
          correct: "1995",
        },
      ],
    };
  },
  methods: {
    checkAnswer(checkValue) {
      if (checkValue === this.questions[0].correct) {
        console.log("correct");
        this.error = null;
        this.correct = true;
      } else {
        console.log("error");
        this.error = true;
      }
    },
  },
  mounted() {
    console.log(this.questions);
  },
};
</script>
