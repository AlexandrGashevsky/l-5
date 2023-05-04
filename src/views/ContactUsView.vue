<template>
    <div class="container">
      <h1>Contact Us</h1>
      <p>Have a question, comment, or concern? Send us a message using the form below.</p>
      <form @submit.prevent="submitForm">
        <div class="form-group">
          <label for="name">Name</label>
          <input type="text" id="name" v-model="name" required>
        </div>
        <div class="form-group">
          <label for="email">Email</label>
          <input type="email" id="email" v-model="email" required>
        </div>
        <div class="form-group">
          <label for="message">Message</label>
          <textarea id="message" v-model="message" required></textarea>
        </div>
        <button type="submit">Send Message</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        name: '',
        email: '',
        message: ''
      }
    },
    methods: {
      submitForm() {
        if (this.name && this.email && this.message) {
          // Send form data to server or email address
          alert('Your message has been sent!')
          this.name = ''
          this.email = ''
          this.message = ''
        } else {
          alert('Please fill out all fields.')
        }
      }
    }
  }
  </script>
  
  <style scoped>
  h1{
    color: rgba(244, 228, 10, 0.945);
  }
  .container {
    background-color: #14000ae5;
    color: #fff;
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
    margin-top: 100px;
    margin-bottom: 100px;
  }
  
  .form-group {
    margin-bottom: 20px;
  }
  
  label {
    display: block;
    font-weight: bold;
    margin-bottom: 5px;
  }
  
  input,
  textarea {
    color: #fff;
    font-weight: 700;
    display: block;
    width: 100%;
    padding: 10px;
    border-radius: 5px;
    border: 2px solid #ccccccce;
    box-sizing: border-box;
    margin-top: 5px;
    background-color: #ffffff00;
    transition-duration: 500ms;
  }

  input:focus,
  textarea:focus{
    box-shadow: 1px #cccccca1;
    outline: none;
    border: 2px solid #cccccc;
  }
  
  button[type="submit"] {
    background-color: #000;
    color: #fff;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
  }
  </style>
  