<template>
  <div class="active-user">
    <h2>Active user's name:</h2>
    <p>{{ activeUser }}</p>
    <h3>Active user's age:</h3>
    <p>{{ activeUserAge }}</p>
  </div>
</template>

<script setup>
const props = defineProps({
  activeUser: {
    type: String,
    required: true,
  },
  activeUserAge: {
    type: Number,
    required: true,
  },
});
</script>

<style scoped>
.active-user {
  border: 1px solid #ccc;
  border-radius: 12px;
  padding: 1rem;
  margin: 1rem 0;
}
</style>
