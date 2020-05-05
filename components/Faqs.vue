<template>
  <section class="faqs" id="faqs">
    <section-header :text="headerText" :title="headerTitle" class="section-header" />
    <div class="toggle-container">
      <div v-for="(item, index) in faqs" :key="item.id" :class="{'is-active' : index == visibleToggle}">
        <button :aria-label="item.title" @click="toggleContainer(index)" class="toggle-header">
          <span>{{ item.title }}</span>
          <svg xmlns="http://www.w3.org/2000/svg" width="18" height="12"><path fill="none" stroke-width="3" d="M1 1l8 8 8-8"/></svg>
        </button>
        <div class="toggle-content">
          <p>{{ item.text }}</p>
        </div>
      </div>
    </div>
    <div class="faqs-link">
      <button-link buttonClass="hilite inline">More Info</button-link>
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
      headerTitle: 'Frequently Asked Questions',
      headerText: 'Here are some of our FAQs. If you have any other questions you\'d like answered, please feel free to email us.',
      faqs: [
        {
          id: 0,
          text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
          title: 'Lorem ipsum dolor?'
        },
        {
          id: 1,
          text: 'Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem.',
          title: 'consectetur adipiscing elit?'
        },
        {
          id: 2,
          text: 'At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga.',
          title: 'ducimus qui blanditiis?'
        },
        {
          id: 3,
          text: 'Temporibus autem quibusdam et aut officiis debitis aut rerum necessitatibus saepe eveniet ut et voluptates repudiandae sint et molestiae non recusandae. Itaque earum rerum hic tenetur a sapiente delectus, ut aut reiciendis voluptatibus maiores alias consequatur aut perferendis doloribus asperiores repellat.',
          title: 'Temporibus autem quibusdam et aut officiis?'
        },
      ],
      visibleToggle: 0
    }
  },
  methods: {
    toggleContainer (index) {
      this.visibleToggle = index;
    }
  }

  
}
</script>

<style>
.faqs {
  margin-left: auto;
  margin-right: auto;
  max-width: 54.2rem;
}

.toggle-container {
  border-top: var(--default-border-color) .1rem solid;
  margin-bottom: 4.8rem;
}

.toggle-header {
  align-items: center;
  background-color: var(--white);
  border-bottom: var(--default-border-color) .1rem solid;
  cursor: pointer;
  display: flex;
  justify-content: space-between;
  outline: 0;
  padding: 2.4rem 0;
  width: 100%;
}

.is-active .toggle-header {
  border: none;
  cursor: default;
}

.toggle-header span {
  font-size: var(--font-size-default);
  font-weight: 500;
}

:not(.is-active) > .toggle-header:hover span {
  color: var(--soft-red);
}

.toggle-header svg {
  display: block;
  stroke: #f2f2f2;
  transition: all .2s;
}
 
.is-active .toggle-header svg {
  stroke: var(--soft-red);
  transform: rotateX(180deg);
}

.toggle-content {
  display: none;
}

.is-active .toggle-content {
  display: block;
}

.faqs .section-header {
  margin-bottom: 3.6rem;
}

.faqs-link {
  display: flex;
  justify-content: center;
}
</style>