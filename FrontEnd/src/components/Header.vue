<template>
    <nav class = nav>
      <div>
        <router-link to="/">Home</router-link> |
        <router-link to="/about">Contacts</router-link>
    </div>
      
    </nav>
  </template>
  
  <script>
  export default {
    // Header component logic goes here
  };
  </script>
  
  <style scoped>
 
  @import url('https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,100;9..40,300&display=swap');
  
  .header {
    background-color: #999; 
    border-radius: 10px; 
    border: 10px;
    padding: 20px;
    }
  
  /* Add the rest of your styles from the CSS file */
  .nav {
    display: flex;
    align-items: center; /* Center items vertically */
    justify-content: center;
    height: 70px;
    background-color: #999;
    border-radius: 10px; 
    padding: 20px;
    margin: 10px;

  }
  
  nav a {
    font-weight: bold;
    color: #2c3e50;
  }
  
  nav a.router-link-exact-active {
    color: #ffffff;
  }
  </style>