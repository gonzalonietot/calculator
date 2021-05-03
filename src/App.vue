<template>
  <div id="app">
    <Calculator />
  </div>
</template>

<script>
import Calculator from './components/Calculator.vue'

export default {
  name: 'App',
  components: {
    Calculator
  }
}
</script>

<style lang="scss">
$cyan: #00e5ff;
#app {
  width: 250px;
  height: 250px;
  margin: auto;
  border: 2px $cyan solid;
  border-radius: 10px;
}
</style>
