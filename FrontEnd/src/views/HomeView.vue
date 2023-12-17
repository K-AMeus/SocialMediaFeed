<template>
  <div class="wrapper">
    <button  @click="Logout" class="logout">Logout</button>
    <div v-for="(post) in getPosts">
      <Post :post="post"/>
    </div>
    <div class="post-buttons">
      <button class="post-btn" @click="openAddPost">Add post</button>
      <button class="post-btn" @click="deleteAllPosts">Delete all</button>
    </div>
  </div>


</template>

<script>
import Post from "@/components/Post";


export default {
  components: {
    Post,
  },

  methods: {
    Logout() {
      fetch("http://localhost:3000/auth/logout", {
        credentials: 'include', 
      })
          .then((response) => response.json())
          .then((data) => {
            console.log(data);
            console.log('jwt removed');
            this.$router.push("/login");
          })
          .catch((e) => {
            console.log(e);
            console.log("error logout");
          });
    },

    openAddPost(){
      this.$router.push("/add-post");
    },

    deleteAllPosts() {
      this.$store.dispatch('deleteAllPostsAct');
    },
  },
  

  computed: {
    getPosts() {
      return this.$store.getters.getPosts;
    },
  },

  mounted() {
    this.$store.dispatch('getAllPostsAct');

  }

};
</script>


<style>
*{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

.logout {
  border-radius: 25px;
  background-color: rgb(56, 100, 196);  
  color: white;
  border: none;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: block;
  font-size: 16px;
  margin: 20px auto;
  cursor: pointer;
  transition-duration: 0.4s;
}

html{
    position: relative;
    min-height: 100%;
}

body {
    font-family: 'Times New Roman', Times, serif, monospace;
}

.wrapper{
  width: 100%;
  display: flex;
  flex-direction: column;
}

.post-buttons{
  display: flex;
  justify-content: space-between;
  width: 650px;
  margin: 30px auto 0;
}

.post-btn{
  border-radius: 25px;
     background-color: rgb(56, 100, 196);  /* Change to your preferred color */
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