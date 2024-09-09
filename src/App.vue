<script setup>
import ResumeSection from './ResumeSection.vue';
import { ref } from 'vue';
import CVData from './assets/data/CV-Ben.json';

let mappedLabels = {
  education: 'Education',
  softSkills: 'Soft Skills',
  experience: 'Experience',
  technicalEnvironment: 'Technical Environment',
  tasks: 'Tasks',
};
</script>

<template>
  <header>
    <h1>Single Page CV</h1>
  </header>

  <main>
    <ResumeSection v-for="(value, key) in CVData" :key="key" :id="key" :title="mappedLabels[key]" :content="value"/>
  </main>
</template>

<style scoped></style>
