<template>
  <section>
    <h1>submitted experiences</h1>
    <button>load submitted experiences</button>
    <ul>
      <li v-for="ex in experiences" :key="ex.id">
        <b>{{ ex.name }}</b> had an experience rating of
        <b :value="ex.score">{{ ex.score }}</b>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  name: 'ShowExperiences',
  props: ['experiences'],
};
</script>

<style scoped>
section h1 {
  text-transform: capitalize;
}
ul {
  list-style-type: none;
  padding-left: 0rem;
  display: flex;
  flex-direction: column;
  width: 100%;
  text-align: left;
  gap: 1rem;
}
ul li {
  border: solid 1px #ccc;
  padding: 1rem;
  width: 96.5%;
}
b[value='Poor'] {
  color: rgb(167, 1, 1);
}
b[value='Average'] {
  color: rgb(255, 196, 0);
}
b[value='Great'] {
  color: rgb(2, 102, 2);
}
</style>
