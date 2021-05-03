<template>
  <div class="container">
    <h3 class="title">
      {{ calculatorText }}
    </h3>
    <div class="operation-container">
      <input
          v-model="operationValue"
          class="operation-value"
          type="text"
          name="operationValue"
          id="operationValue"
          readonly />
      <label for="operationValue" />
    </div>
    <div class="buttons-container">
      <button v-for="(item, i ) in operators" :key="i" class="button operation-button"> {{ item.operator }}</button>
      <button v-for="(number, index) in numbers" :key="index" class="button"> {{ number }}</button>
      <button class="button result-button"> {{ result }}</button>
    </div>
    <div>
      <button class="clean"> {{ cleanText }} </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Calculator',
  data() {
    return {
      operationValue: '',
      calculatorText: 'Calculadora',
      numbers: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, '.'],
      operators: [
        { id: 1, operator: '/' },
        { id: 2, operator: 'x' },
        { id: 3, operator: '+' },
        { id: 4, operator: '-' }
      ],
      result: '=',
      cleanText: 'Borrar'
    }
  },
}
</script>

<style scoped lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Antonio:wght@100&display=swap');
  $blue: #039be5;

  .container {
    .title {
      font-family: 'Antonio', sans-serif;
      text-align: center;
      color: $blue;
      border: 1px solid;
    }
    .operation-container {
      margin-bottom: 5px;
      text-align: center;
      input {
        width: 200px;
      }
    }
    .buttons-container {
      text-align: center;
      .button {
        width: 50px;
      }
    }
    .clean {
      width: 250px;
      margin-top: 10px;
    }
  }

</style>
