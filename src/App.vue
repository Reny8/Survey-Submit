<template>
  <TheHeader />
  <SurveyForm />
</template>

<script>
import SurveyForm from './components/SurveyForm.vue';
import TheHeader from './components/TheHeader.vue';
export default {
  name: 'App',
  components: {
    SurveyForm,
    TheHeader,
  },
};
</script>

<style>
html {
  background-color: #efefef;
}
body {
  margin: 0rem;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
section {
  box-shadow: rgba(0, 0, 0, 0.2) 0px 2px 7px -1px,
    rgba(0, 0, 0, 0.14) 0px 1px 1px 0px, rgba(0, 0, 0, 0.12) 0px 1px 3px 0px;
  margin: 2rem 4rem;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 1rem 3rem;
  background-color: white;
}
button {
  text-transform: capitalize;
  border: none;
  font-weight: 600;
  padding: 1rem 4rem;
  border-radius: 3px;
  background-color: #360b59;
  box-shadow: rgba(0, 0, 0, 0.2) 0px 2px 7px -1px,
    rgba(0, 0, 0, 0.14) 0px 1px 1px 0px, rgba(0, 0, 0, 0.12) 0px 1px 3px 0px;
  color: white;
}
button:hover {
  background-color: #360b5996;
  cursor: pointer;
  transition-duration: 500ms;
}
</style>
