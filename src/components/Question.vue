<script setup>
import { defineProps, defineEmits } from "vue";

const emit = defineEmits(["selectedOption"]);

const { question } = defineProps(["question"]);

const selectedOption = (isCorrect) => {
  emit("selectedOption", isCorrect);
};
</script>

<template>
  <div class="question-container">
    <h1 class="question">{{ question.text }}</h1>
  </div>
  <ul class="options-container">
    <li
      v-for="option in question.options"
      :key="option.id"
      class="option"
      @click="selectedOption(option.isCorrect)"
    >
      <p class="option-label">{{ option.label }}</p>
      <p class="option-value">{{ option.text }}</p>
    </li>
  </ul>
</template>

<style scoped>
.question-container {
  margin-top: 20px;
}
.question {
  font-size: 40px;
  margin-bottom: 20px;
}
.option {
  display: flex;
  margin-bottom: 20px;
  cursor: pointer;
}
.option-label {
  background-color: bisque;
  width: 60px;
  height: 50px;
  font-size: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.option-value {
  background-color: rgb(244, 239, 239);
  width: 100%;
  font-size: 30px;
  padding: 0 20px;
}
</style>
