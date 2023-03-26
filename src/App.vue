<script setup>
import ActiveUser from './components/ActiveUser.vue';
import UserData from './components/UserData.vue';
import { ref } from 'vue';

const users = ref([{ username: 'Max', age: 30 }]);

const addUser = (userData) => {
  users.value.push(userData);
};
</script>

<template>
  <div id="app">
    <ActiveUser
      v-for="user in users"
      :active-user="user.username"
      :active-user-age="user.age"
    />

    <UserData @add-user="addUser" />
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
