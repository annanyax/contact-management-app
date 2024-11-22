<template>
    <header>
      <h1>Contact Management</h1>
      <input
        type="text"
        placeholder="Search contacts..."
        v-model="search"
        @input="$emit('update-search', search)"
      />
    </header>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    emits: ['update-search'],
    setup(_, { emit }) {
      const search = ref('');
      return { saerch };
    },
  };
  </script>
  
  <style scoped></style>
  