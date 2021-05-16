<template>
  <div>
    <h3 class="title">
      Calculadora
    </h3>
    <div class="input-container">
      <input
          v-model="value"
          type="text"
          name="value"
          id="value"
          readonly />
      <label for="value" />
    </div>
    <div class="buttons-container">
      <button
          v-for="(item, index) in buttonsValue"
          :key="index"
          type="button"
          class="button"
          @click="addValues(item)">
        {{ item }}
      </button>
      <button
          type="button"
          class="button result-button"
          @click="calculate">
        {{ resultButton }}
      </button>
    </div>
    <div style="text-align: center">
      <button
          class="clean"
          @click="clean"
          type="button"
      >
        Borrar
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Calculator',
  data() {
    return {
      buttonsValue: [ 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, ".", "/", "*","+", "-" ],
      resultButton: '=',
      value: '',
    }
  },
  methods: {
    addValues (value) {
      this.value += value;
    },
    calculate() {
      //add validations
      this.value = eval(this.value.toString());
    },
    clean() {
      this.value = '';
    }
  }
}
</script>

<style scoped lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Antonio:wght@100&display=swap');
  $blue: #039be5;
  $light-blue-lighten-2: #4FC3F7;

  .title {
    font-family: 'Antonio', sans-serif;
    text-align: center;
    color: $blue;
    border: 1px solid;
    margin-top: -1px;
    border-radius: 5px;
  }
  .input-container {
    margin-bottom: 30px;
    text-align: center;
    input {
      width: 320px;
      height: 30px;
      font-size: 16px;
      font-weight: bold;
    }
  }
  .buttons-container {
    text-align: center;
    .button {
      height: 30px;
      width: 60px;
      background-color: #E6E6E6;
      text-decoration: none;
      white-space: nowrap;
      cursor: pointer;
      border: 1px solid #999;
      border: transparent;
      border-radius: 2px;
      margin: 3px;
      font-size: 16px;
      font-weight: bold;
    }
    .button:hover {
      background-color: $light-blue-lighten-2;
      color: white;
    }
  }
  .clean {
    width: 320px;
    margin-top: 10px;
    height: 30px;
    border: 1px solid;
    border: transparent;
    border-radius: 2px;
    color: white;
    background-color: $light-blue-lighten-2;
    cursor: pointer;
    font-size: 14px;
    font-weight: 700;
  }

</style>
