<template>
  <AboutComponent :membres="11"></AboutComponent>
  <InfiniteScrollComponent :items="['Nicolas', 'Mimie', 'Stephanie', 'Mireille', 'Damien', 'Christian', 'Solène', 'Janick', 'Sylvain']" />
</template>

<script>
// @ is an alias to /src
import AboutComponent from '@/components/AboutComponent.vue';
import InfiniteScrollComponent from '@/components/InfiniteScrollComponent.vue';

export default {
name: 'AboutView',
components: {
  AboutComponent,
  InfiniteScrollComponent,
},
}
</script>