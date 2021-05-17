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
$cyan: #50C7BF;
#app {
  width: 350px;
  height: 300px;
  margin: auto;
  border: 1px $cyan solid;
  border-radius: 5px;
}
</style>
