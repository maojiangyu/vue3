<template>
    <!-- static -->
    <!-- <greeting-message name="John" last-name="Doe" /> -->
  
    <!-- dynamic with data properties -->
    <!-- <greeting-message :name="fName" :last-name="lName" /> -->
    <p v-bind:class="['bold', 'italic', isValid ? 'valid' : 'invalid']">{{ fName }}</p>
    <a v-bind:href="link">Vue {{ version }} API Reference</a>
    <p>{{ link }}</p>
    <p v-pre>{{ link }}</p>
    <p>name: {{ name }}</p>
    <input type="text" @input="getInput">
  </template>
  
  <script>
  //import GreetingMessage from './components/GreetingMessage'
  
  export default {
    //components: { GreetingMessage },
    data() {
      return {
        fName: 'Jane',
        lName: 'Doe',
        link: 'https://vuejs.org/api/',
        dataProperty: 'invalid',
        isValid: false,
        version: 3,
        name:''
      }
    },

    methods: {
      getInput() {
        this.name = event.target.value
      }
    }
  }
  </script>

  <style>
    .bold    { font-weight: bolder }
    .italic  { font-style:  italic }
    .valid   { color: forestgreen  }
    .invalid { color: crimson      }
</style>