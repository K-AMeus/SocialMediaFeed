<template>
    <div class="card">
      <h1>Add Post</h1>
      <form @submit.prevent="addPost">
        <textarea v-model="body" placeholder="Post Body" required></textarea>
        <button type="submit">Submit</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        body: ''
      }
    },
    methods: {
      async addPost() {
        const post = {
          body: this.body
        }
        try {
          const response = await fetch('http://localhost:3000/post/add-post', {
            method: 'POST',
            headers: {
              'Content-Type': 'application/json'
            },
            body: JSON.stringify(post)
          });
  
          if (!response.ok) {
            throw new Error(`HTTP error!: ${response.status}`);
          } else {
            this.body = '';
            this.$router.push('/'); 
          }
        } catch (error) {
          console.error(error);
        }
      }
    }
  }
  </script>
  
  
  
  <style scoped>
  .card {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 80%;
    margin: 20px auto;
    padding: 40px;
    border: 1px solid #ddd;
    border-radius: 10px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  }
  
  form {
    display: flex;
    flex-direction: column;
    width: 100%;
  }
  
  input, textarea {
    margin-bottom: 10px;
    height: 40px;
  }
  
   button {
     border-radius: 25px;
     background-color: rgb(56, 100, 196); 
     color: white;
     border: none;
     padding: 15px 32px;
     text-align: center;
     text-decoration: none;
     display: inline-block;
     font-size: 16px;
     margin: 4px 2px;
     cursor: pointer;
     transition-duration: 0.4s;
   }
  
  </style>