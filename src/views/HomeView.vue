<template>
  <HomeComponent>
  </HomeComponent>
  <RevealComponent></RevealComponent>
  <InfiniteScrollComponent></InfiniteScrollComponent>
</template>

<script>
// @ is an alias to /src
import HomeComponent from '@/components/HomeComponent.vue';
import InfiniteScrollComponent from '@/components/InfiniteScrollComponent.vue';
import RevealComponent from '@/components/RevealComponent.vue';

export default {
  name: 'HomeView',
  components: {
    HomeComponent,
    InfiniteScrollComponent,
    RevealComponent
  }
}
</script>
