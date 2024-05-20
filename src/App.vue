<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <div class="app">
    <HelloWorld msg="You did it!" />
  </div>
</template>

<style>
body {
  background-color: rgb(255, 189, 199);
}

.app {
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: center;
}
</style>
