<template>
  <section class="email-signup">
   <div class="email-signup-wrapper">
      <div class="email-signup-header">
        <h2>Best Ways to Find Your True Sole Mate</h2>
        <p>35,000+ Already Joined</p>
      </div>
      <form v-if="!formSubmitted" @submit.prevent="formSubmit()">
        <div class="input-wrapper" :class="{'form-error' : $v.email.$error}">
          <input aria-label="Email" id="email" type="email" v-model="email" @blur="$v.email.$touch()" placeholder="Enter your email address">
          <div class="error-message" v-if="$v.email.$error">
            <i aria-hidden="true">!</i>
            <em v-if="!$v.email.required">Please add an email!</em>
            <em v-if="!$v.email.url">Whoops, make sure it's an email!</em>
          </div>
        </div>
        <button>Join Now!</button>
      </form>
      <div v-else>
        <p>Thank you. Your information has been submitted.</p>
      </div>
   </div>
  </section>
</template>

<script>
import { required, email } from "vuelidate/lib/validators";
export default {
  data () {
    return {
      email: null,
      formSubmitted: false
    }
  },
  methods: {
    formSubmit () {
      this.$v.$touch();
      if (!this.$v.$invalid) {
        // this.$v.$reset();
        this.formSubmitted = true;
      } else {
        console.log("Invalid Form");
      }
    }
  },
  validations() {
    return {
      email: { required, email }
    };
  }
}
</script>

<style scoped>
section {
  background-color: var( --soft-red);
  color: var(--white);
  padding: 7.5rem 3.2rem 4rem;
  text-align: center;
}

h2, p {
  color: var(--white);
}

p {
  line-height: 1;
  margin-bottom: 1.6rem;
  text-transform: uppercase;
}

h2 {
  font-size: 2rem;
}

i {
  align-items: center;
  background-color: var(--soft-red);
  border-radius: 100%;
  color: var(--white);
  display: flex;
  font-style: normal;
  font-weight: 500;
  height: 2rem;
  justify-content: center;
  position: absolute;
  right: 1.3rem;
  top: 1.3rem;
  width: 2rem;
}

.input-wrapper {
  border-radius: var(--border-radius);
  position: relative;
  margin-bottom: 1.6rem;
}

.form-error {
  background-color: var(--soft-red);
  border-radius: var(--border-radius);
  box-shadow: 0 0 0 .2rem var(--soft-red);
  text-align: left;
}

.error-message {
  padding: .4rem 2rem;
}

.email-signup-header {
  display: flex;
  flex-direction: column-reverse;
  margin-bottom: 3.2rem;
}

.email-signup-wrapper {
  margin-left: auto;
  margin-right: auto;
  max-width: 54rem;
}

input, button {
  appearance: none;
  border-radius: var(--border-radius);
  border: 0;
  height: 4.4rem;
  width: 100%;
}

input {
  background-color: var(--white);
  font-size: 1.6rem;
  padding: 0 2rem;
}

button {
  background-color: white;
  border: var(--soft-red) .2rem solid;
  color: var(--soft-red);
  font-size: 1.6rem;
  font-weight: 500;
  transition: all .2s;
}

button:hover {
  background-color: var(--white);
  border-color: var(--soft-red);
  color: var(--soft-red);
}

@media (min-width: 1024px) {
  form {
    display: grid;
    grid-column-gap: 2rem;
    grid-template-columns: 2fr 1fr;
  }
}
</style>