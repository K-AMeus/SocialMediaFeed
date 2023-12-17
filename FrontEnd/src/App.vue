<template>
  <div class="app-container">
    <LeftSidebar />
    <div class="content-container">
      <nav>
        <router-link to="/">Home</router-link> |
        <router-link to="/about">Contacts</router-link>
      </nav>
      <router-view />
    </div>
    <RightSidebar />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
import LeftSidebar from "@/components/LeftSidebar.vue"; // Import LeftSidebar
import RightSidebar from "@/components/RightSidebar.vue"; // Import RightSidebar

export default {
  components: {
    Header, 
    Footer,
    LeftSidebar, // Register LeftSidebar
    RightSidebar, // Register RightSidebar
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
  display: flex; /* Use flexbox layout */
  justify-content: space-between; /* Space out the sidebars and main content */
}

.content-container {
  flex-grow: 1; /* Allows the main content to take up the remaining space */
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
