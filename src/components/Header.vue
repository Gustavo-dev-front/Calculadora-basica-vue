<script setup>
const {estado}  = defineProps(["estado"]);
</script>

<template>
  <header class="Header">
    <h1>Minha calculadora</h1>
    <span>O resultado desta <strong>{{ estado.operadores[estado.operadorAtual] }}</strong> é <strong>{{estado.resultado}}</strong></span>
  </header>
</template>