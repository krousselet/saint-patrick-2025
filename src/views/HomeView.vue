<template>
  <HomeComponent>
  </HomeComponent>
  <RevealComponent></RevealComponent>
  <GroupsComponent></GroupsComponent>
  <InfiniteScrollComponent :items="['Bière', 'Fête', 'Amis', 'Saint Patrick', 'Trèfles', 'Bellevesvre', 'Skull Darts 71', 'Fléchettes']" />
</template>

<script>
// @ is an alias to /src
import HomeComponent from '@/components/HomeComponent.vue';
import GroupsComponent from '@/components/GroupsComponent.vue';
import RevealComponent from '@/components/RevealComponent.vue';
import InfiniteScrollComponent from '@/components/InfiniteScrollComponent.vue';

export default {
  name: 'HomeView',
  components: {
    HomeComponent,
    InfiniteScrollComponent,
    RevealComponent,
    GroupsComponent,
  }
}
</script>
