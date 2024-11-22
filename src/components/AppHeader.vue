<template>
    <header>
      <h1>Contact Management</h1>
      <input
        type="text"
        placeholder="Search contacts..."
        v-model="searchInput"
        @input="$emit('update-search', searchInput)"
      />
    </header>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    props: ['search'],
    emits: ['update-search'],
    setup(props, { emit }) {
      const searchInput = ref(props.search || '');
      return { searchInput };
    },
  };
  </script>
  
  <style scoped></style>
  