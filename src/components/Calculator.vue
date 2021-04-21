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
          <button v-for="(numb, index) in numbers" :key="index" class="button"> {{ numb }}</button>
          <button class="button" style="color: white; background-color: #E53935"> {{ result }}</button>
          <button v-for="(op, ind) in operators" :key="ind" class="button" style="background-color: #8BC34A; color: white"> {{ op }}</button>
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
      operators: ['/', 'x', '' + '+', '-'],
      result: '=',
      cleanText: 'Borrar'
    }
  },
}
</script>

<style scoped lang="scss">
  .container {
    .title-container {
      background-color: #0277BD;
      height: 35px;
      border-radius: 5px;
      .title {
        text-align: center;
        color: white;
      }
    }
    .input-value, .button-container, .clean-container {
      text-align: center;
      margin-top: 10px;
      .operation-value, .clean {
        width: 90%;
      }
      .clean {
        background-color: #0277BD;
        color: white;
        height: 35px;
        border-radius: 5px;
      }
    }
    .button-container {
      margin: 4px;
      .button {
        width: 70px;
        height: 30px;
      }
      .button:hover {
        background-color: #37474F;
        color: white;
      }
    }
  }
</style>
