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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>

<style scoped lang="scss">
.title-container {
  margin: 25px auto;
}
h1 {
  letter-spacing: 2px;
}
</style>