<template>
    <div class="footer">
      <!-- Your footer content goes here -->
       <a class = footerText> The End</a>
       <a class = footerText> © Copyright 2023 | HMM: Hanna Mona Meus </a>
    </div>
  </template>
  
  <script>
  export default {
    // Footer component logic goes here
  };
  </script>
  
  <style scoped>

  
  .footer{
     text-align: center;
  background-color: #999;
  border-radius: 10px;
  border: 10px;
  padding: 20px;
  margin-top: auto; /* Make the footer stick to the bottom */
  margin-bottom: 10px;
  }
  
  .footerText {
    color: #ffffff;
    display: block; /* Make the element a block-level element */
    margin-bottom: 10px;
  }
  </style>