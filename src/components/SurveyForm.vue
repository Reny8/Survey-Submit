<template>
  <section>
    <h1>How was your learning experience?</h1>
    <form @submit.prevent="submitForm">
      <div class="name-container">
        <label for="name">your name</label>
        <input name="name" type="text" v-model.trim="name" />
      </div>
      <h3>My learning experience was...</h3>

      <div class="radio-container" v-for="radio in radioValues" :key="radio.id">
        <input type="radio" :value="radio.value" v-model="radioSelection" />
        <p>{{ radio.value }}</p>
      </div>
      <button type="submit" :disabled="filled">submit</button>
    </form>
  </section>
</template>

<script>
export default {
  name: 'SurveyForm',
  props: ['addExperience'],
  computed: {
    filled() {
      return this.name === '' || this.radioSelection === null;
    },
  },
  data() {
    return {
      name: '',
      radioSelection: null,
      radioValues: [
        {
          id: new Date().toISOString(),
          value: 'Poor',
        },
        {
          id: new Date().toISOString(),
          value: 'Average',
        },
        {
          id: new Date().toISOString(),
          value: 'Great',
        },
      ],
    };
  },
  methods: {
    submitForm() {
      this.addExperience({
        id: new Date().toISOString(),
        name: this.name,
        score: this.radioSelection,
      });
      this.name = '';
      this.radioSelection = null;
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  width: 39%;
}
form div.radio-container {
  display: flex;
  align-items: baseline;
}
label {
  text-transform: capitalize;
}
form div.name-container {
  display: flex;
  align-items: baseline;
  flex-direction: column;
  gap: 0.5rem;
  width: 100%;
}
form div.name-container input {
  padding: 0.3rem 1rem;
  width: 90%;
}
form div.radio-container p {
  margin: 0.2rem;
}

form button {
  margin-top: 0.8rem;
}
</style>
