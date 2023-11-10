<template>
  <div class="container">
    <h2>Calculadora aritmética</h2>
    <input v-model.number="num1" type="number" placeholder="Número 1" />
    <input v-model.number="num2" type="number" placeholder="Número 2" />
    <select v-model="operation">
      <option value="add">Adicionar</option>
      <option value="sub">Subtrair</option>
      <option value="mul">Multiplicar</option>
      <option value="div">Dividir</option>
    </select>
    <p>O resultado é: {{ calculate() }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: 'add'
    };
  },
  methods: {
    calculate() {
      switch (this.operation) {
        case 'add':
          return Number(this.num1) + Number(this.num2);
        case 'sub':
          return Number(this.num1) - Number(this.num2);
        case 'mul':
          return Number(this.num1) * Number(this.num2);
        case 'div':
          return Number(this.num1) / Number(this.num2);
        default:
          return 0;
      }
    }
  }
};
</script>

<style scoped>
.container {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 50vh; 
  max-width: 600px;
  margin: auto; 
  padding: 20px;
  border: 5px solid;
  border-radius: 20px;
  background-color: rgb(7, 228, 7);
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.9);
}

h2 {
  color: white;
  font-weight: 700;
  margin-bottom: 20px;
}

input[type="number"],
select {
  display: block;
  width: 100%;
  padding: 10px;
  margin-bottom: 10px;
  font-size: 16px;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.9);
}

p {
  font-size: 30px;
  font-weight: bold;
  margin-top: 20px;;
}

</style>
