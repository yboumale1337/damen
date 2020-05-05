<template>
  <main>
    <hero />
    <about />
    <features />
    <faqs />
  </main>
</template>
<script>

import about from '../components/about.vue'
import Faqs from '../components/Faqs.vue'
import Features from '../components/Features.vue'
import Hero from '../components/Hero.vue'
export default {
  components: {about, Faqs, Features, Hero }
}
</script>
<style>
main {
  padding: 0 3.2rem;
  overflow: hidden;
}
main > section {
  margin-bottom: 15.5rem;
}

@media (min-width: 1024px) {
  main {
    margin: 0 auto;
    max-width: 118rem;
    overflow: visible;
  }

  main > section {
    margin-bottom: 20rem;
  }
}
</style>
