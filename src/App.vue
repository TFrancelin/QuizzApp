<template>
  <div class="ctr">
    <questions-component v-if="questionsAnswered < questions.length"></questions-component>
    <result-component v-else></result-component>
    <button class="reset-btn" type="button">Reset</button>
  </div>
</template>
<script>
import QuestionsComponent from "./components/Questions.vue"
import ResultComponent from "./components/Result.vue"
export default {
  name: 'App',
  components: {
    QuestionsComponent, 
    ResultComponent,
  },
  data() {
    return {
      questionsAnswered: 0,
      questions: [
        {
          q: "What is 2 + 2?",
          answers: [
            {
              text: "4",
              is_correct: true,
            },
            {
              text: "3",
              is_correct: false,
            },
            {
              text: "Fish",
              is_correct: false,
            },
            {
              text: "5",
              is_correct: false,
            }
          ]
        },
        {
          q: "How many letters are in the word 'Banana'?",
          answers: [
            {
              text: "5",
              is_correct: false
            },
            {
              text: "7",
              is_correct: false,
            },
            {
              text: "6",
              is_correct: true,
            }
          ] 
        },
        {
          q: "Find the missing letter: C_ke",
          answers: [
            {
              text: "e",
              is_correct: false,
            },
            {
              text: "a",
              is_correct: true
            },
            {
              text: "i",
              is_correct: false
            }
          ]
        }
      ],
      results: [
        {
          min: 0,
          max: 2,
          title: "Try again!",
          desc: "Do a little more studying and you may succeed!",
        },
        {
          min: 3,
          max: 3,
          title: "Wow, you're a genius!",
          desc: "Studying has definitely paid off for you!",
        }
      ]
    }
  },
}
</script>

