<template>
  <section class="about" id="about">
    <section-header :text="headerText" :title="headerTitle" class="section-header" />
    <div class="cards">
      <div v-for="card in about" :key="card.id" class="card">
        <div class="card-content">
          <img width="170" :src="require('../assets/images/' + card.image)" alt="">
          <h3>{{ card.title }}</h3>
        </div>
        <div class="card-footer">
          <button-link :url="card.url" buttonClass="hilite">{{ card.buttontext }}</button-link>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import ButtonLink from './ButtonLink.vue'
import SectionHeader from './SectionHeader.vue'
export default {
  components: { ButtonLink, SectionHeader },
  data () {
    return {
      headerTitle: 'How Does It Work?',
      headerText: 'You\'re just 3 steps away from a great date',
      about: [
        {
          id: 0,
          image: 'popular.svg',
          title: 'Tell us who you are!',
          buttontext: 'Join Now!'
        },
        {
          id: 1,
          image: 'getaway.svg',
          title: 'Find the right person',
          buttontext: 'Read More'
        },
        {
          id: 2,
          image: 'love_is_in_the_air.svg',
          title: 'Start Dating',
          buttontext: 'Read More'
        }
      ]
    }
  }
}
</script>

<style>
.card {
  background-color: var(--white);
  border-radius: var(--border-radius);
  box-shadow: var(--drop-shadow);
  margin-bottom: 4rem;
  margin-left: auto;
  margin-right: auto;
  max-width: 38rem;
  overflow: hidden;
  text-align: center;
  width: 100%;
}
.card-content {
  padding: 4.8rem 0 4rem;
}

.card-content h3 {
  font-size: var(--font-size-md);
}

.card-content img {
  margin-bottom: 3.6rem;
}

.card-footer {
  background: var(--white) url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='280' height='4'%3E%3Cpath fill='%23495DCF' fill-opacity='.2' fill-rule='evenodd' d='M0 4a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm280 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-17 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-35 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-35 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-35 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-18 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-17 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm122 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-35 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-35 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zm-70 0a2 2 0 1 1 0-4 2 2 0 0 1 0 4zM88 4a2 2 0 1 1 0-4 2 2 0 0 1 0 4zM70 4a2 2 0 1 1 0-4 2 2 0 0 1 0 4zM53 4a2 2 0 1 1 0-4 2 2 0 0 1 0 4zM35 4a2 2 0 1 1 0-4 2 2 0 0 1 0 4zM18 4a2 2 0 1 1 0-4 2 2 0 0 1 0 4z'/%3E%3C/svg%3E") top center repeat-x;
  padding: 2.5rem;
}

.card-footer::before {
  content: " ";
  height: 1rem;
  position: relative;
  width: 100%;
}

.about .section-header {
  margin-bottom: 3.6rem;
}

@media (min-width: 1024px) {
  .cards {
    display: grid;
    grid-column-gap: 3.2rem;
    grid-template-columns: 1fr 1fr 1fr;
    margin-left: auto;
    margin-right: auto;
    max-width: 91.2rem;
  }
  .card:nth-child(2n) {
    transform: translateY(3.2rem);
  }

  .card:last-of-type {
    transform: translateY(6.4rem);
  }
}
</style>
