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
    <p></p>
    <div class="card">{{ content }}</div>

      <p>
        <button @click="activeStep = 'step-a'">Step A</button>
        <button @click="activeStep = 'step-b'">Step B</button>
      </p>

        <keep-alive>
          <component :is="activeStep" />
        </keep-alive>
    <div class="card">{{ content }}
      <h2>
        <slot name="cardTitle">Fallback Title</slot>
      </h2>
      <slot>Fallback content</slot>
    </div>
  </template>
  
  <script>
  //import GreetingMessage from './components/GreetingMessage'
  import StepA from "./StepA.vue";
  import StepB from "./StepB.vue";
  export default {
    //components: { GreetingMessage },

    props:['content'],
    components: {
      StepA, StepB
    },

    data() {
      return {
        fName: 'Jane',
        lName: 'Doe',
        link: 'https://vuejs.org/api/',
        dataProperty: 'invalid',
        isValid: false,
        version: 3,
        name:'',
        activeStep: 'step-a'
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
    .card {
      max-width: 250px;
      text-align: center;
      margin: 2rem auto;
      padding: .6rem .8rem;
      border: .1rem solid #94A3B8;
      color: #64748B;
    }
</style>