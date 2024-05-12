<template>
  <div class="container">
    <h1 :class="headingClasses" :style="headingStyles">{{ message }}</h1>
    
    <form @submit.prevent="handleSubmit">
      <label for="inputText">Masukan Teks: </label>
      <input type="text" id="inputText" v-model="inputText" :class="inputClasses" :style="inputStyles" />
      
      <button type="submit" :class="buttonClasses">Ubah Pesan</button>
    </form>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue';

const message = ref('Hello, Vue.js 3!');
const inputText = ref('');

const headingClasses = reactive({
  'red-text': false,
  'bold-text': true,
});

const headingStyles = reactive({
  fontSize: '2rem',
});

const inputClasses = reactive({
  'input-styling': true,
});

const inputStyles = reactive({
  padding: '0.5rem',
  borderRadius: '5px',
  border: '1px solid #007BFF',
  fontSize: '1rem',
});

const buttonClasses = reactive({
  'button-styling': true,
});

const handleSubmit = () => {
  message.value = inputText.value;
  inputText.value = '';
};
</script>

<style scoped>
h1 {
  color: rgb(25, 250, 0);
  font-style: italic;
}

.container {
  max-width: 600px;
  margin: 0 auto;
  text-align: center;
  padding-top: 50px;
  }

.red-text {
  color: red;
}

.bold-text {
  font-weight: bold;
}

.input-styling {
  margin-top: 10px;
}

.button-styling {
  margin-top: 10px;
  background-color: #007BFF;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.button-styling:hover {
  background-color: #0056b3;
}
</style>