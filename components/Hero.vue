<template>
  <section class="hero">
    <div class="hero-img">
      <img src="../assets/images/illustration-hero.svg" alt="">
    </div>
    <div class="hero-content">
      <h1>Dream of finding love</h1>
      <p>More singles who are more your style.<br/>40,000,000 singles worldwide and 3 million messages send daily</p>
        <button-link class="button-group" buttonClass="hilite" url="#">Download the App</button-link> 
    </div>
  </section>
</template>
<script>
import ButtonLink from './ButtonLink.vue'
export default {
  components: {
    ButtonLink
  },
  data () {
    return {
      title: 'Hero'
    }
  }
}
</script>
<style scoped>

.hero-img {
  margin-bottom: 9.1rem;
  position: relative;
}

.hero-img img {
  height: auto;
  transform: scale(1.14) translateY(1.7rem);
  width: 100%;
}

.hero-content {
  text-align: center;
}

h1 {
  font-size: var(--font-size-lg);
  line-height: 1.3;
  margin-bottom: 1.9rem;
}

p {
  margin-bottom: 3.2rem;
  padding: 0 .9rem;
}

.button-group {
  display: grid;
  grid-column-gap: 20px;
  background-color: #f40057;
  color: white;
  text-align: center;
}


@media (min-width: 1024px) {
  .hero {
    align-items: center;  
    display: grid;
    grid-column-gap: 10rem;
    grid-template-columns: 1fr 1fr;
  }
  .hero-content {
    order: 0;
    text-align: left;
  }

  h1 {
    font-size: 5rem;
    line-height: 1;
    margin-bottom: 1.9rem;
  }

  .hero-content p {
    padding: 0;
  }

  .hero-img {
    margin: 0;
    order: 1;
  }

  .hero-img img {
    transform: scale(1.3) translateX(3rem) translateY(3rem);
  }

  .button-group {
    width: 66%;
  }
}
</style>
