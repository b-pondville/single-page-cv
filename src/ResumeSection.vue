<script setup>
const props = defineProps({
  id: String,
  title: String,
  content: Array || String,
});

console.log(props.content)

</script>

<template>
  <section v-if="props.id == 'education'" :id="props.id">
    <h2>Education</h2>
    <div v-for="(diploma, key) in props.content">
      <h3>{{ diploma.title }}</h3>
      <h4>{{ diploma.institution }} | {{ diploma.diploma }}</h4>
    </div>
  </section>

  <section v-if="props.id == 'softSkills'" :id="props.id">
    <h2>Soft skills</h2>
    <ul>
      <li v-for="skill in props.content">{{ skill }}</li>
    </ul>
  </section>

  <section v-if="props.id == 'experience'" :id="props.id">
    <h2>Experience</h2>
    <div v-for="(job, key) in props.content">
      <h3>{{ job.title }} - {{ job.dates }}</h3>
      <h4 v-if="job.type == 'Permanent'">{{ job.company }}</h4>
      <h4 v-else-if="job.type == 'Freelance'">Freelance at {{ job.company }}</h4>
      <h4 v-else>{{ job.type }}</h4>
      <h5>Tasks:</h5>
      <ul>
        <li v-for="task in job.tasks">{{ task }}</li>
      </ul>

      <h5>Technical environment:</h5>
      <ul>
        <li v-for="techno in job.technicalEnvironment">{{ techno }}</li>
      </ul>
    </div>
  </section>
</template>

<style scoped>
section {
  margin-bottom: 5px;
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 10px;
}

h2 {
  font-size: 28px;
  color: #333;
  border-bottom: 2px solid #e0e0e0;
  padding-bottom: 10px;
  margin-bottom: 20px;
  font-family: 'Roboto', Tahoma, Geneva, Verdana, sans-serif;
  font-weight: 900;
}

h3 {
  font-size: 22px;
  margin: 50px 0 10px 0;
  color: #444;
}

h4 {
  font-size: 18px;
  margin: 5px 0 10px 0;
  color: #777;
  font-weight: normal;
}

h5 {
  font-size: 18px;
  color: #555;
  margin: 20px 0 0 0;
  font-weight: bold;
}

ul {
  list-style-type: none;
  padding: 0;
  margin: 10px 0;
}

ul li {
  margin: 5px 0;
  font-size: 16px;
  color: #555;
  display: flex;
  align-items: center;
  font-family: 'Roboto', Tahoma, Geneva, Verdana, sans-serif;
}

ul li::before {
  content: "•";
  color: #ff6b6b;
  font-weight: bold;
  display: inline-block;
  width: 1em;
  margin-right: 10px;
}

div {
  margin-bottom: 20px;
}

@media screen and (max-width: 768px) {
  section {
    padding: 15px;
  }

  h2 {
    font-size: 24px;
  }

  h3 {
    font-size: 20px;
  }

  h4 {
    font-size: 16px;
  }

  ul li {
    font-size: 14px;
  }
}
</style>