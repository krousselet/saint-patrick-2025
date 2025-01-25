<template>
  <nav>
    <router-link to="/">Home</router-link>
    <router-link to="/about">Description</router-link>
    <router-link to="/details">Details</router-link>
  </nav>
  <router-view/>
</template>

<style lang="scss">
// GENERAL
body {
  background-color: black;
}

h1 {
  font-family: "UnifrakturCook", serif;
}

// MEDIA QUERIES
@media (min-width:320px) and (max-width:991px) {
  h1 {
    font-size: 1.8rem;
  }
}
@media (min-width:992px) and (max-width:2048px) {
  h1 {
    font-size: 3.6rem;
  }
}

@media (min-width:2049px) {
  h1 {
    font-size: 5.5rem;
  }
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  color: white;
}

@media (min-width:320px) and (min-width: 991px) {
  main {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 1fr;
  }

}
.images-container {
  margin-bottom: 25px;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr;
    align-items: center;
  }
nav {
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 80px;

  a {
    font-weight: bold;
    color: #2c3e50;
    text-decoration: none;

    &.router-link-exact-active {
      color: rgba(255, 0, 0, 0.833);
    }
  }
}
</style>
