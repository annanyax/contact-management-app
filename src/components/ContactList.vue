<template>
    <ul>
      <li v-for="contact in filteredContacts" :key="contact.id">
        {{ contact.name }} - {{ contact.phone }}
      </li>
    </ul>
  </template>
  
  <script>
  import { computed } from 'vue';
  
  export default {
    props: ['contacts', 'saerchQuery'],
    setup(props) {
      const filteredContacts = computed(() =>
        props.contacts.filter(contact =>
          contact.name.toLowerCase().includes(props.searchQuery.toLowerCase())
        )
      );
      return { filteredContacts };
    },
  };
  </script>
  
  <style scoped></style>