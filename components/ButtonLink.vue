<template>
  <a :href="url" :class="buttonClass"><slot></slot></a>
</template>

<script>
export default {
props: {
  url: {
    type: String,
    required: false,
    default: '#'
  },
  buttonClass: {
    type: String,
    required: false
  }
}
}
</script>

<style scoped>
button, a {
  font-size: var(--font-size-default);
  font-weight: 500;
}

button, a {
  cursor: pointer;  
}

a {
  background-color: var(--white);
  border-radius: var(--border-radius);
  border: var(--white) .2rem solid;
  box-shadow: var(--drop-shadow);
  color: var(--dark-grey-text);
  display: block;
  line-height: 4.8rem;
  text-align: center;
  text-decoration: none;
  transition: all .2s;
  width: 100%;
}

a.inline {
  display: inline-flex;
  padding: 0 3rem;
  width: auto;
}

a.center {
  margin-left: auto;
  margin-right: auto;
}

a:hover {
  border-color: var(--very-dark-blue);
  color: var(--very-dark-blue);
}

.hilite {
  background-color: var( --soft-red);
  border-color: var( --soft-red);
  color: var(--white);
}

a.hilite:hover {
  background-color: var(--white);
  color: var( --soft-red); 
}

.red {
  color: var(--white);
  background-color: var(--soft-red);
  border-color: var(--soft-red);
  line-height: 3.6rem;
}

a.red:hover {
  color: var(--soft-red);
  border-color: var(--soft-red);
  background-color: var(--white);
}

.clear {
  border-color: var(--white);
  color: var(--white);
  background-color: rgba(0,0,0,0);
}

a.clear:hover {
  background-color: var(--white);
  border-color: var(--white);
  color: var(--very-dark-blue);
}
</style>