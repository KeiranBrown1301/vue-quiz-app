<script setup>
import Question from "../../components/Question.vue";
import QuizHeader from "../../components/QuizHeader.vue";
import { useRoute } from "vue-router";
import { ref, watch, computed } from "vue";
import quizzes from "../data/quizes.json";

const route = useRoute();
const quizId = parseInt(route.params.id);
const quiz = quizzes.find((q) => q.id === quizId);
const currentQuestionIndex = ref(0);

// Here computed is used as the equivilant of what is belw with the questionStatus and watch use.
const questionStatus = computed(
  () => `${currentQuestionIndex.value}/${quiz.questions.length}`
);

// const questionStatus = ref(
//   `${currentQuestionIndex.value}/${quiz.questions.length}`
// );
// watch(
//   () => currentQuestionIndex.value,
//   () => {
//     questionStatus.value = `${currentQuestionIndex.value}/${quiz.questions.length}`;
//   }
// );
</script>

<template>
  <div>
    <QuizHeader :questionStatus="questionStatus" />
    <div>
      <Question :question="quiz.questions[currentQuestionIndex]" />
    </div>
    <button @click="currentQuestionIndex++">Next Question</button>
  </div>
</template>
