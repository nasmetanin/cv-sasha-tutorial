<template>
  <div class="home page">
    <IntroComp />
  </div>
</template>

<script>
// @ is an alias to /src
import IntroComp from '@/components/IntroComp.vue';

export default {
  name: 'HomeView',
  components: {
    IntroComp
  }
}
</script>
