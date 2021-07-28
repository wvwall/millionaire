<template>
  <div class="container">
    <Question
      v-for="(quest, index) in filterQuest"
      :key="'domanda' + index"
      :questions="quest.question"
    />
    <div
      class="container-answ"
      v-for="(quest, index) in filterQuest"
      :key="'risposta' + index"
    >
      <Answers
        @check="checkAnswer"
        v-for="(date, index) in quest.answers"
        :key="'data' + index"
        :answer="date"
      />
    </div>
    <div class="container_result">
      <i :class="{ active: correct }" class="fas fa-check-circle"></i>
      <i :class="{ active: error }" class="fas fa-times-circle"></i>
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
      correct: false,
      error: false,
      number: null,
      db_questions: [
        {
          id: 1,
          question: "In che anno è nato Wall?",
          answers: ["1995", "1997", "1994", "1998"],
          correct: "1995",
        },
        {
          id: 2,
          question: "In che anno si svolti gli Europei 2020?",
          answers: ["2021", "2020", "2022", "2019"],
          correct: "2021",
        },
        {
          id: 3,
          question: "In che anno si sono svolte le Olimpiadi 2020?",
          answers: ["2021", "2020", "2022", "2019"],
          correct: "2021",
        },
      ],
      // questions: [
      //   {
      //     id: 3,
      //     question: "In che anno si sono svolte le Olimpiadi 2020?",
      //     answers: ["2021", "2020", "2022", "2019"],
      //     correct: "2021",
      //   },
      // ],
    };
  },
  computed: {
    filterQuest: function () {
      return this.db_questions.filter(
        (question) => question.id === this.number
      );
    },
  },
  methods: {
    checkAnswer(checkValue) {
      console.log(checkValue);
      if (checkValue === this.filterQuest[0].correct) {
        console.log("correct");
        this.error = false;
        this.correct = true;
        // this.number = this.getRandom(1, this.db_questions.length);
        console.log(this.number);
        console.log(this.filterQuest);
      } else {
        console.log("error");
        this.error = true;
        this.correct = false;
        this.questions = null;
      }
    },
    getRandom(min, max) {
      return Math.floor(Math.random() * (max - min) + min);
    },
  },
  mounted() {
    this.number = this.getRandom(1, this.db_questions.length);
    console.log(this.number);
    console.log(this.filterQuest);
  },
};
</script>
