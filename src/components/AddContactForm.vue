<template>
 <div>
    <h2>Add Contact Form</h2>
    <form @submit.prevent="addContact">
      <input type="text" v-model="name" placeholder="Name" />
      <input type="text" v-model="phone" placeholder="Phone Number" />
      <button type="submit">Add Contact</button>
      <p v-if="error">{{ error }}</p>
    </form>
 </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    emits: ['add-contact'],
    setup(_, { emit }) {
      const name = ref('');
      const phone = ref('');
      const error = ref('');
      
  
      const addContact = () => {
        if (!name.value || !phone.value) {
        error.value = 'Both fields are required';
        return;
      }
          emit('add-contact', { id: Date.now(), name: name.value, phone: phone.value });
          name.value = '';
          phone.value = '';
          error.value = '';
        };
  
      return { name, phone, error, addContact };
    },
  };
  </script>
  
  <style scoped></style>
  