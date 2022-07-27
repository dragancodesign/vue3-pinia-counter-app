<template>
<div class="about">
<h1>About</h1>
<h3>This is VueJS 3 a simple Counter app.</h3>
<button
    @click="storeCounter.increaseCount"
  class="counter-button">
  {{
  storeCounter.count
  }}
  </button>
</div>
</template>

<script setup>
import { useCounterStore } from '@/stores/counter'

const storeCounter = useCounterStore() 
</script>

<style>
body {
    background-color: lavender;
}
.counter-button {
    font-size: 50px;
    background-color: aquamarine;
}
</style>