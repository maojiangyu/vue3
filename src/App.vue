<script>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import test from './components/test.vue';
import Test from './components/test.vue';

</script>

<script setup>
import { ref } from 'vue';

const x = ref(0)
const awesome = ref(0)

function increment() {
  x.value ++
}
</script>

<template>
  <header>
  </header>

  <main>
    <!-- <TheWelcome /> -->
    <p>Using text interpolation: {{x ? "xxxx" : "yyyy"}}</p>
    <p>Using v-html directive: <span v-html="rawHtml"></span></p>
    <button @click="increment">{{ x }}</button>
    <button @click.middle="awesome = !awesome">Toggle</button>
    <h1 v-if="awesome">Vue is awesome!</h1>
    <h1 v-else>Oh no 😢</h1>
  </main>
  <Test></Test>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
