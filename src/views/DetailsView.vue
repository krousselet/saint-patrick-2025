<template>
    <DetailsComponent>
    </DetailsComponent>
    <LeprechaunComponent></LeprechaunComponent>
</template>

<script>
// @ is an alias to /src
import DetailsComponent from '@/components/DetailsComponent.vue'
import LeprechaunComponent from '@/components/LeprechaunComponent.vue';

export default {
  name: 'DetailsView',
  components: {
    DetailsComponent,
    LeprechaunComponent,
  }
}
</script>