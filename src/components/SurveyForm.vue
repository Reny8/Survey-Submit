<template>
  <section>
    <h1>How was your learning experience?</h1>
    <form>
      <div class="name-container">
        <label for="name">your name</label>
        <input name="name" type="text" />
      </div>
      <h3>My learning experience was...</h3>

      <div class="radio-container" v-for="radio in radioValues" :key="radio.id">
        <input type="radio" :value="radio.value" />
        <p>{{ radio.value }}</p>
      </div>
      <button type="submit">submit</button>
    </form>
  </section>
</template>

<script>
export default {
  name: 'SurveyForm',
  data() {
    return {
      name: '',
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
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
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
}
form div.radio-container p {
  margin: 0.2rem;
}

form button {
  margin-top: 0.8rem;
}
</style>
