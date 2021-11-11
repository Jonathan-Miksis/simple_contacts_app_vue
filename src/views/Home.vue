<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for: contact for contacts
  </div>
</template>

<style></style>

<script>
  export default {
    data: function () {
      return {
        message: "Welcome to Vue.js!",
        indexContacts: [],
      };
    },
    created: function () {},
    methods: {

    },
  };
</script>