<script setup>
import ResumeSection from './ResumeSection.vue';
import { ref } from 'vue';

async function fetchCVData() {
  try {
    const response = await fetch('src/assets/data/CV-Ben.json');
    const data = await response.json();
    return data;
  } catch (error) {
    console.error('Error fetching CV data:', error);
  }
}

let cvData = ref(null);
fetchCVData().then((data) => {
  cvData.value = data;
});

console.log(cvData);

</script>

<template>
  <header>
    <h1>Single Page CV</h1>
  </header>

  <main>
    <ResumeSection :title="''" :content="''" />
  </main>
</template>

<style scoped></style>
