<template>
  <nav class="glass-nav">
    <router-link to="/">Home</router-link>
    <router-link to="/about">Description</router-link>
    <router-link to="/details">Details</router-link>
  </nav>
  <router-view/>
</template>

<style lang="scss">

.glass-nav {
  position: relative;
  z-index: 5;
  background: rgb(0, 0, 0); /* Semi-transparent white */
  border-radius: 15px;
  backdrop-filter: blur(50px); /* Glass effect */
  box-shadow: 0 4px 10px rgba(28, 195, 40, 0.804);
  transition: all 0.3s ease-in-out;
}


// GENERAL
body {
  background-color: black;
}

.title-container  {
  font-family: "MedievalSharp", serif;
  font-weight: 400;
  font-style: normal;
}
ul {
  margin: 0;
  padding: 0;
  
  li {
    list-style: none;
    margin: 0;
    padding: 0;
    margin: 1vw auto;
  }
}

a {
  text-decoration: none;
  color: white;
  font-family: "MedievalSharp", serif;
  font-size: 1.5rem;
}

.font {
  font-family: "MedievalSharp", serif;
}

// SCROLLBARS

::-webkit-scrollbar {
  width: .2vw;
  height: 10px;
}

::-webkit-scrollbar-thumb {
  background: lime;
  border-radius: 5px;
}

::-webkit-scrollbar-track {
  background: #f1f1f1;
  border-radius: 5px;
}

/* Target specific elements */
.my-scrollable-element::-webkit-scrollbar {
  width: 8px;
}

.my-scrollable-element::-webkit-scrollbar-thumb {
  background: #444;
  border-radius: 4px;
}

.my-scrollable-element::-webkit-scrollbar-track {
  background: #ddd;
}

// MEDIA QUERIES
@media (min-width:320px) and (max-width:991px) {
  h1 {
    font-size: 1.8rem;
  }

  a {
    font-size: 19px;
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



//KEYFRAMES

@keyframes opacity {
  100% {
    opacity: 1;
  }
}
</style>
