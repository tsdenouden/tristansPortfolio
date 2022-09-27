<template>
  <router-view/>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200&display=swap');

#app {
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

html {
  scroll-behavior: smooth;
  border-bottom: 15px solid lightseagreen;
}

body {
  background-color: whitesmoke;
  margin: 0px;
  padding: 0px;
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
