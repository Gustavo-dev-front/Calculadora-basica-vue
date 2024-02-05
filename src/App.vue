<script setup>
import "../node_modules/bootstrap/dist/css/bootstrap.min.css";
import Header from "./components/Header.vue";
import Form from "./components/Form.vue";
import { reactive } from "vue";

const estado = reactive({
  n1: 0,
  n2: 0,
  resultado: 0,
  operadorAtual: "+",
  operadores: {
    "+": "soma",
    "-": "subtração",
    "*": "multiplicação",
    "/": "divisão",
  }
});

const calcular = () => {
  const { operadorAtual } = estado;
  switch (operadorAtual) {
    case "+":
      return (+estado.n1) + (+estado.n2);
    case "-":
      return (+estado.n1) - (+estado.n2);
    case "*":
      return (+estado.n1) * (+estado.n2);
    case "/":
      return (+estado.n1) / (+estado.n2);
  }
}

const changeResultado = () => {
  const resultado = calcular();
  if (isFinite(resultado)) return estado.resultado = resultado;

  estado.resultado = "Error";
}

</script>

<template>
  <div class="App container">
    <Header :estado="estado"></Header>
    <Form :estado="estado" :changeResultado="changeResultado"></Form>
  </div>
</template>
<style scoped></style>
