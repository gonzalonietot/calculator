<template>
  <div>
    <div class="container">
      <div class="title-container">
        <h3 class="title">
          {{ calculatorText }}
        </h3>
      </div>
      <div class="input-value">
        <label for="operationValue" />
        <input
            v-model="operationValue"
            class="operation-value"
            type="text"
            name="operationValue"
            id="operationValue"
            readonly />
      </div>
      <div class="button-container">
          <button v-for="(number, index) in numbers" :key="index" class="button"> {{ number }}</button>
          <button class="button result-button"> {{ result }}</button>
          <button v-for="op in operators" :key="op.id" class="button operation-button"> {{ op.operator }}</button>
      </div>
      <div class="clean-container">
        <button class="clean"> {{ cleanText }} </button>
      </div>
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
  $red: #E53935;
  $white: #FFFFFF;
  $blue: #1976D2;
  $green: #4CAF50;

  .container {
    .title-container {
      background-color: $blue;
      height: 35px;
      border-radius: 5px;
      .title {
        text-align: center;
        color: $white;
        transform: translate(5px, 5px);
      }
    }
    .input-value, .button-container, .clean-container {
      text-align: center;
      margin-top: 10px;
      .operation-value, .clean {
        width: 93%;
      }
      .clean {
        background-color: $blue;
        color: $white;
        height: 35px;
        border-radius: 5px;
      }
    }
    .button-container {
      margin: 4px;
      .button {
        width: 70px;
        height: 30px;
        margin: 2px 2px;
      }
      .result-button {
        transition: box-shadow 300ms ease-in-out, color 300ms ease-in-out;
        background-color: $red;
        color: $white;
        &:hover,
        &:focus {
          box-shadow: 0 0 40px 40px $green inset;
          outline: 0;
        }
      }
      .operation-button {
        transition: box-shadow 300ms ease-in-out, color 300ms ease-in-out;
        background-color: $green;
        color: $white;
      }
    }
  }
</style>
