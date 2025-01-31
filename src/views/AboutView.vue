<template>
  <AboutComponent :membres="13"></AboutComponent>
  <InfiniteScrollComponent :items="['Nicolas', 'Emilie', 'Stephanie', 'Mireille', 'Damien', 'Christian', 'Solène', 'Aurore', 'Janick', 'Sylvain', 'Kevin']" />
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