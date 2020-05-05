<template>
  <section class="features-wrapper" id="features">
    <section-header :text="headerText" :title="headerTitle" class="section-header" />
    <ul class="nav-bars">
      <li v-for="(item, index) in featuredItems" :key="item.slug" :class="{'isSelected' : currentSlide == index}">
        <button @click="setCurrentSlide(index)">
          {{ item.title }}
        </button>
      </li>
    </ul>
    <div v-for="(slide, index) in featuredItems" :key="slide.id" class="slide">
      <template v-if="index == currentSlide">
        <div class="feature-image" :class="'slide-' + index">
          <img :src="require('~/assets/images/' + slide.image)" alt="">
          <!-- <div aria-hidden="true" class="treatment"></div> -->
        </div>
        <div class="feature-content">
          <section-header :text="slide.text" :title="slide.title" header="h3" class="section-header" />
          <button-link buttonClass="hilite">More Info</button-link>
        </div>
      </template>
    </div>
  </section>
</template>

<script>
import ButtonLink from '~/components/ButtonLink.vue'
import SectionHeader from '~/components/SectionHeader.vue'

export default {
  components: { ButtonLink, SectionHeader },
  data () {
    return {
      currentSlide: 0,
      headerTitle: 'Amazing Features',
      headerText: 'To find meaningful connections , dates, and life partners.',
      featuredItems: [
        {
          id: 0,
          image: 'illustration-features-tab-1.svg',
          slug: 'Simple to use',
          text: 'Simple steps to follow to have a matching connection',
          title: 'Simple to use'
        },
        {
          id: 1,
          image: 'community.svg',
          slug: 'Cool community',
          text: 'BuddyPress network is full of cool members',
          title: 'Cool community'
        }
      ]
    }
  },
  methods: {
    setCurrentSlide (value) {
      this.currentSlide = value
    }
  }
}
</script>

<style>
.isSelected {
  color: var(--soft-red);
}

.features-wrapper .section-header {
  margin-bottom: 3.6rem;
}

.features-wrapper button {
  background-color: var(--white);
  color: var(--very-dark-blue);
}

.features-wrapper img {
  height: auto;
  width: 100%;
}

.feature-image {
  position: relative;
}


.feature-image,
.features-wrapper .nav-bars {
  margin-bottom: 7rem;
}

.features-wrapper .nav-bars,
.features-wrapper .nav-bars li {
  border-color: var(--default-border-color);
}

.features-wrapper .nav-bars li.isSelected::after {
  background-color: var(--soft-red);
  bottom: 0;
  content: "";
  height: .4rem;
  left: 50%;
  position: absolute;
  transform: translateX(-50%);
  width: 46%;
}

@media (min-width: 1024px) {
  .slide {
    align-items: center;
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  .feature-content a {
    display: inline-flex;
    padding: 0 2rem;
    width: auto;
  }

  

  .feature-image {
    margin-bottom: 0;
  }

  .features-wrapper .nav-bars {
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin-left: auto;
    margin-right: auto;
    max-width: 73rem;
  }

  .features-wrapper .nav-bars button:hover {
    color: var(--soft-red);
  }

  .features-wrapper .nav-bars li {
    border: 0;
  }

  .features-wrapper .nav-bars li.isSelected::after {
    left: 0;
    transform: translateX(0);
    width: 100%;
  }

  .feature-content {
    padding-left: 11rem;
  }

  .feature-content .section-header {
    text-align: left;
  }

  .feature-image .treatment {
    left: calc(-40vw + 18rem);
  }

  .feature-image.slide-0 .treatment {
    top: 6rem;
  }

  .feature-image.slide-1 .treatment {
    top: 15rem;
  }

  .feature-image.slide-2 .treatment {
    top: 18rem;
  }

  .feature-image .treatment::after {
    right: -18rem;
  }
}
</style>
