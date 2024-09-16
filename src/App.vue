<script setup>
import ResumeSection from "./assets/components/ResumeSection.vue";
import CVData from "./assets/data/CV-Ben.json";
</script>

<template>
  <header>
    <h1>Benjamin Pondville</h1>
  </header>

  <main>
    <ResumeSection
      v-for="(value, key) in CVData"
      :key="key"
      :id="key"
      :content="value"
    />
  </main>
</template>

<style scoped></style>
