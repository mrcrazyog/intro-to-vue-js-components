<template>
  <div class="user-data">
    <h2>Input new user:</h2>
    <form @submit.prevent="addUser">
      <label for="username">Username</label>
      <input id="username" v-model="enteredUsername" />
      <label for="age">Age</label>
      <input id="age" v-model.number="enteredAge" />
      <button type="submit">Add User</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const emit = defineEmits(['addUser']);
const enteredUsername = ref('');
const enteredAge = ref('');

const addUser = () => {
  const userData = {
    username: enteredUsername.value,
    age: enteredAge.value,
  };
  emit('addUser', userData);
  enteredUsername.value = '';
  enteredAge.value = '';
};
</script>

<style scoped>
.user-data {
  border: 1px solid #ccc;
  border-radius: 12px;
  padding: 1rem;
  margin: 1rem 0;
  background-color: #807b92;
}
</style>
