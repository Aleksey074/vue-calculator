<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    {{ message }}
    <input type="text" v-model.number="operand1" />
    <input type="text" v-model.number="operand2" />

    = {{ result }}
    
    <hr />

    <button @click="result = operand1 + operand2">+</button>
    <button @click="result = operand1 - operand2">-</button>
    <button @click="divide" :disabled="operand2 == 0">/</button>
    <button @click="multiply(operand1, operand2)">*</button>
    <button @click="degree(operand1, operand2)">Возвести в степень</button>
    <button @click="integerDivision(operand1, operand2)" :disabled="operand2 == 0">Целочисленное деление</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      message: "Калькулятор",
      operand1: 0,
      operand2: 0,
      result: 0,
    };
  },
  methods: {
    divide() {
      this.result = this.operand1 / this.operand2;
    },
    multiply(op1, op2) {
      this.result = op1 * op2;
    },
    degree(op1, op2) {
      this.result = op1;
      for (let i = 1; i < op2; i++) {
        this.result *= op1;
      }
      return this.result;
    },
    integerDivision(op1, op2) {
      if (op1 / op2 >= 0) this.result = Math.floor(op1 / op2);
      else this.result = Math.ceil(op1 / op2);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
