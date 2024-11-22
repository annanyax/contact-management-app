<template>
  <!-- Root container -->
  <div id="app">   
    <AppHeader :search="search" @update-search="updateSearch" />
    <ContactList :contacts="filteredContacts" />
    <AddContactForm @add-contact="addContact" />
  </div>
</template>

<script>
import { ref } from 'vue'; // Composition API utilities
import AppHeader from './components/AppHeader.vue';
import ContactList from './components/ContactList.vue';
import AddContactForm from './components/AddContactForm.vue';

</script>

<style scoped>

</style>

