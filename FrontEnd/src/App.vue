<template>
<div class="main">
        <Header />

  <div class="app-container">
    <LeftSidebar />
    <div class="content-container">
      <router-view />
    </div>
    <RightSidebar />
  </div>
        <Footer />

</div>
</template>

<script>
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
import LeftSidebar from "@/components/LeftSidebar.vue"; 
import RightSidebar from "@/components/RightSidebar.vue"; 

export default {
  components: {
    Header, 
    Footer,
    LeftSidebar, 
    RightSidebar, 
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.app-container {
  display: flex;
  justify-content: space-between; 
  min-height: 100vh; 

}


.content-container {
  flex-grow: 1; /* Allows the main content to take up the remaining space */
  text-align: center;
  color: #2c3e50;
  
}

.main{
  flex-grow: 1; /* Allows the main content to take up the remaining space */
  text-align: center;
  color: #2c3e50;
  min-height: 100vh;
}
</style>

