<template>
  <main>
    <div class="title-container">
      <h1>Skull Darts 71</h1>
    </div>
    <div class="text">
      <p>Présente pour sa seconde édition...</p>
    </div>
  </main>
</template>

<script>
export default {
  name: 'HelloComponent',
  props: {
    title: String
  }
}
</script>

<style scoped lang="scss">
.title-container {
  margin: 40px auto;
  opacity: 0;
  animation: opacity .5s .2s ease forwards
}

h1 {
  letter-spacing: 2px;
}

.text {
  opacity: 0;
  animation: opacity .5s .5s ease forwards;
  text-transform:uppercase;
}

@media (min-width: 320px) and (max-width:991px) {
  p {
    letter-spacing: 3px;
    font-size: 1.1rem;
  }
}

@media (min-width: 992px) and (max-width:2048px) {
  p {
    letter-spacing: 6px;
    font-size: 2.2rem;
  }
}

@media (min-width: 2049px) {
  p {
    letter-spacing: 10px;
    font-size: 2.9rem;
  }
}

p {
  font-family: 'Times New Roman', Times, serif;
}

@keyframes opacity {
  100% {
    opacity: 1;
  }
}
</style>