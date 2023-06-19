<script setup>
import { defineProps } from "vue";
import { RouterLink } from "vue-router";

const { correctAnsCount, totalQuestions } = defineProps([
  "correctAnsCount",
  "totalQuestions",
]);
</script>

<template>
  <div class="results">
    <p>your results...</p>
    <h1>{{ correctAnsCount }}/{{ totalQuestions }}</h1>
    <RouterLink to="/">Go back</RouterLink>
  </div>
</template>
<style scoped>
.results {
  text-align: center;
  padding: 100px 0;
}
.results p {
  font-size: 48px;
}
.results h1 {
  font-size: 80px;
}
</style>
