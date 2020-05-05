<template>
  <div>
    <component :is="header">
      {{ title }}
    </component>
    <p>{{ text }}</p>
  </div>
</template>

<script>
export default {
  props: {
    header: {
      type: String,
      default: 'h2'
    },
    text: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
div {
  margin: 0 auto;
  max-width: 54rem;
  text-align: center;
}
h2, h3 {
  font-size: var(--font-size-md);
  margin-bottom: 1.2rem;
}

@media (min-width: 1024px) {
  h2, h3 {
    font-size: 3.2rem;
  }
}
</style>
