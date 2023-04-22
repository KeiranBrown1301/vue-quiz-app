<script setup></script>

<template>
  <div>
    <header>
      <h4>Question 1/3</h4>
      <div class="bar">
        <div class="completion"></div>
      </div>
    </header>
    <div>
      <div class="question-container">
        <h1 class="question">What is the chemical value of table salt?</h1>
      </div>
      <div class="questions-container"></div>
    </div>
  </div>
</template>

<style scoped>
header {
  margin-top: 20px;
}

header h4 {
  font-size: 30px;
}

.bar {
  width: 300px;
  height: 50px;
  border: 3px solid bisque;
}

.completion {
  height: 100%;
  width: 0%;
  background-color: bisque;
}
</style>
