<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
  <RouterView />
</template>

<style scoped>

nav {
  margin-top: -400px ;
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: white;
  padding: 20px 50px;
  background: rgb(78, 73, 73);
}

nav a.router-link-exact-active {
  color: rgb(126, 160, 126)
}

nav a {
  font-size: 30px;
  color: white;
  text-decoration: none;
}



</style>
