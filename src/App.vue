<template>
  <!-- Root container -->
  <div id="app">   
    <AppHeader :search="search" @update-search="updateSearch" />
    <ContactList :contacts="filteredContacts" />
    <AddContactForm @add-contact="addContact" />
  </div>
</template>

<script>
import { ref, computed } from 'vue'; // Composition API utilities
import AppHeader from './components/AppHeader.vue';
import ContactList from './components/ContactList.vue';
import AddContactForm from './components/AddContactForm.vue';

export default {
  components: { AppHeader, ContactList, AddContactForm },
  setup() {

    // Load contacts from localStorage and predefined contacts
    const contacts = ref(JSON.parse(localStorage.getItem('contacts')) || [
      { id: 1, name: 'Mario Rossi', phone: '3331234567' },
      { id: 2, name: 'Anna Bianchi', phone: '3209876543' },
    ]);


    const search = ref(''); // Search contact query

    // Filtered contacts for search query
    const filteredContacts = computed (() =>
      contacts.value.filter(contact =>
        contact.name.toLowerCase().includes(search.value.toLowerCase())
      )
    );

    // Add a new contact
    const addContact = (contact) => {
      contacts.value.push(contact);
      localStorage.setItem('contacts', JSON.stringify(contacts.value)); // Save to localStorage
    };

    // Update filtered contacts for search query
    const updateSearch = (query) => {
      search.value = query;
    };

    return { contacts, search, filteredContacts, addContact, updateSearch };
  },
};

</script>

<style scoped>

</style>

