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

export default {
  components: { AppHeader, ContactList, AddContactForm },
  setup() {

    const contacts = ref(JSON.parse(localStorage.getItem('contacts')) || []); // Load contacts from localStorage
    const search = ref(''); // Search contact query

    // Filtered contacts for search query
    const filteredContacts = ref([]);
    filteredContacts.value = contacts.value;

    // Add a new contact
    const addContact = (contact) => {
      contacts.value.push(contact);
      localStorage.setItem('contacts', JSON.stringify(contacts.value)); // Save to localStorage
    };

    // Update filtered contacts for search query
    const updateSearch = (query) => {
      search.value = query;
      filteredContacts.value = contacts.value.filter(contact =>
     contact.name.toLowerCase().includes(query.toLowerCase())
     );
    };

    return { contacts, search, filteredContacts, addContact, updateSearch };
  },
};

</script>

<style scoped>

</style>

