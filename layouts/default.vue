<template>
  <div>
    <nav v-if="activeMenu" class="mobile-nav">
      <div class="mobile-nav__header" aria-hidde="true">
        <img width="148" height="60" src="../assets/images/Asset.svg" alt="">
        <button @click="toggleMenu()" aria-label="Menu toggle button">
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="15"><path fill="#FFF" fill-rule="evenodd" d="M8 5.379L13.303.075l2.122 2.122L10.12 7.5l5.304 5.303-2.122 2.122L8 9.62l-5.303 5.304-2.122-2.122L5.88 7.5.575 2.197 2.697.075 8 5.38z" /></svg>
        </button>
      </div>
      <ul @click="toggleMenu()" class="site-links nav-bars">
        <li v-for="link in navLinks" :key="link.slug">
          <a :href="link.route">{{ link.text }}</a>
        </li>
      </ul>
      <button-link buttonClass="clear">Join Now!</button-link>
      <ul class="social-links">
        <li v-for="link in socialMediaLinks" :key="link.id">
          <img :src="require('../assets/images/' + link.image)" :alt="link.id">
        </li>
      </ul>
    </nav>
    <header>
     <img width="148" height="60" src="../assets/images/Asset.svg" alt="">
      <button @click="toggleMenu()" aria-hidden="true">
        <svg xmlns="http://www.w3.org/2000/svg"><path fill="#242A45" fill-rule="evenodd" d="M0 0h18v3H0V0zm0 6h18v3H0V6zm0 6h18v3H0v-3z" /></svg>
      </button>
      <nav aria-hidden="true">
        <ul>
          <li v-for="link in navLinks" :key="link.slug">
          <a :href="link.route">{{ link.text }}</a>
        </li>
          <li>
            <button-link buttonClass="red inline">Join Now!</button-link>
          </li>
        </ul>
      </nav>
    </header>
    <nuxt />
    <email-signup />
    <footer>
      <div class="footer-wrapper">
        <img width="148" height="60" src="../assets/images/footerlogo.svg" alt="">
        <nav>
          <ul class="site-links">
            <li v-for="link in navLinks" :key="link.slug">
              <a :href="link.route">{{ link.text }}</a>
            </li>
          </ul>

          <ul class="social-links">
            <li v-for="link in socialMediaLinks" :key="link.id">
              <img :src="require('../assets/images/' + link.image)" :alt="link.id">
            </li>
          </ul>
        </nav>
      </div>

    </footer>
  </div>
</template>
<script>
import ButtonLink from '../components/ButtonLink.vue'
import EmailSignup from '../components/EmailSignup.vue'
export default {
  components: {ButtonLink, EmailSignup},
  data () {
    return {
      activeMenu: false,
      navLinks: [
        {
          text: 'About',
          route: '/#about',
          slug: 'About'
        },
        {
          text: 'Features',
          route: '/#features',
          slug: 'Features'
        },
        {
          text: 'FAQ',
          route: '/#faqs',
          slug: 'FAQ'
        }
      ],
      socialMediaLinks: [
        {
          id: 'facebook',
          image: 'icon-facebook.svg',
          route: 'https://www.facebook.com'
        },
        {
          id: 'twitter',
          image: 'icon-twitter.svg',
          route: 'https://www.twitter.com'
        }
      ]
    }
  },
  methods: {
    toggleMenu () {
      this.activeMenu = !this.activeMenu
    }
  }
}
</script>
<style>
header {
  align-items: center;
  display: flex;
  justify-content: space-between;
  margin: 0 auto;
  max-width: 118rem;
  padding: 4rem 3.2rem 7rem;
}
header button,
header button svg {
  height: 1.5rem;
  padding: 0;
  width: 1.8rem;
}

header button {
  margin-top: .3rem;
}

header nav {
  display: none;
}

.mobile-nav {
  background-color: hsla(229, 31%, 21%,0.95);;
  color: #fff;
  display: flex;
  flex-direction: column;
  height: 100vh;
  left: 0;
  padding: 4rem 3.2rem;
  position: fixed;
  top: 0;
  width: 100vw;
  z-index: 1;
}

.mobile-nav button {
  background-color: rgba(0,0,0,0);
}

.mobile-nav__header {
  align-items: center;
  display: flex;
  justify-content: space-between;
  margin-bottom: 4rem;
}
.mobile-nav .site-links {
  margin-bottom: 1rem;
}
.mobile-nav .social-links {
  align-items: center;
  display: flex;
  justify-content: center;
  margin-top: auto;
}

.mobile-nav .social-links li {
  margin: 0 1rem;
}

.mobile-nav a {
  color: #fff;
  text-decoration: none;
  text-transform: uppercase;
}

.mobile-nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

footer {
  background-color: #f40057;
  text-align: center;
  padding: 4rem 3.2rem;
}

.footer-wrapper > svg {
  display: inline-block;
  margin-bottom: 2rem;
}

footer ul {
  list-style: none;
  padding: 0;
  text-transform: uppercase;
}

footer .site-links {
  font-size: 1.6rem;
  line-height: 3;
  margin-bottom: 2rem;
}

footer .social-links {
  align-items: center;
  display: flex;
  justify-content: center;
}

footer .social-links li {
  margin: 0 2rem;
}

footer .logo-text {
  fill: var(--white);
}

footer a {
  color: var(--white);
  text-decoration: none;
}

@media (min-width: 1024px) {
  header {
    padding: 5rem 3.2rem 11rem 4rem;
  }

  header button, 
  .mobile-nav {
    display: none;
  }

  header nav {
    display: flex;
  }

  header nav ul {
    align-items: center;
    display: flex;
    list-style: none;
    padding: 0;
    margin: 0;
  }

  header nav li {
    padding: 0;
    margin: 0 0 0 5rem;
  }

  header nav a {
    text-decoration: none;
    text-transform: uppercase;
    font-size: 1.4rem;
    color: var(--greyish-blue);
    font-weight: 500;
  }

  header nav a:hover {
    color: var(--soft-red);
  }

  footer a:hover,
  .footer-wrapper > svg {
    color: var(--soft-red);
    margin: 0;
  }

  .footer-wrapper {
    align-items: center;
    display: flex;
    max-width: 118rem;
    margin: 0 auto;
    text-align: left;
  }

  footer .site-links, footer .social-links, footer nav {
    align-items: center;
    display: flex;
    margin: 0;
  }

  footer .site-links li {
    margin-right: 4rem;
  }

  footer nav {
    flex-grow: 1;
    margin-left: 6.4rem;
  }

  footer .social-links {
    margin-left: auto;
  }
}
</style>
