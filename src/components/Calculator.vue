<template>
  <div>
    <div class="title-container">
        <h1 class="title">
          Calculadora
        </h1>
    </div>
    <div class="container">
      <div class="input-value">
        <label for="operationValue" />
        <input
            v-model="operationValue"
            class="operation-value"
            type="text"
            name="operationValue"
            id="operationValue">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Calculator',
  data() {
    return {
      operationValue: ''
    }
  }
}
</script>

<style scoped lang="scss">
  .title-container {
    background-color: #1E88E5;
    height: 75px;
    .title {
      color: #ECEFF1;
      position: absolute;
      margin-left: 10px;
      font-size: 30px;
    }
  }
  .container {
    .input-value {
      position: absolute;
      margin-top: 10px;
      .operation-value {
        width: 350px;
        height: 40px;
      }
    }
  }

</style>
