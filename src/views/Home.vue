<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="contact in contacts" v-bind:key="contact.id">
      <p>First Name: {{ contact.first_name }}</p>
      <p>Last Name: {{ contact.last_name }}</p>
      <p>Email: {{ contact.email }}</p>
      <p>Phone Number: {{ contact.phone_number }}</p>
      <hr>
    </div>
  </div>
</template>

<style></style>

<script>
import axios from 'axios';
  export default {
    data: function () {
      return {
        message: "Welcome to My Contacts",
        contacts: [],
      };
    },
    created: function () {
      this.indexContacts();
    },
    methods: {
      indexContacts: function() {
        console.log('getting the contacts from the API');
        axios.get("/contacts").then(response => {
        console.log(response.data);
        this.contacts = response.data
      });
    },
  },
};
</script>