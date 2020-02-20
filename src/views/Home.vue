<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="contact in contacts">
      <h2>{{ contacts.first_name }}</h2>
    </div>
    <p>{{ contacts }}</p>
  </div>
 

</template>

<style>
</style>

<script>
let axios = require("axios");

export default {
  data: function() {
    return {
      message: "Welcome to Vue.js!",
      contacts: []
    };
  },
  created: function() {
    axios.get("/api/contacts")
    .then(response => {
    this.contacts = response.data;
    });
  },
  methods: {

  }
};
</script>