<template>
    <ul>
      <li v-for="contact in contacts" :key="contact.id">
        {{ contact.name }} - {{ contact.phone }}
      </li>
    </ul>
  </template>
  
  <script>
  import { computed } from 'vue';
  
  export default {
    props: ['contacts'],
    setup(props) {
      return { contacts: computed(() => props.contacts) };
    },
  };
  
  </script>
  
  <style scoped></style>