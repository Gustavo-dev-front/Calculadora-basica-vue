<script setup>
const { estado, changeResultado } = defineProps(["estado", "changeResultado"]);

</script>

<template>
  <form class="Form py-3">
    <div class="row">
      <div class="col-md-4 d-flex align-items-center">
        <input type="number" placeholder="primeiro número" class="form-control" :value="estado.n1"
          @input="({ target }) => { estado.n1 = target.value; changeResultado() }">
      </div>

      <span class="col-md fs-2 d-flex align-items-center justify-content-center">{{estado.operadorAtual}}</span>

      <div class="col-md-4 d-flex align-items-center">
        <input type="number" placeholder="segundo número" class="form-control" :value="estado.n2"
          @input="({ target }) => { estado.n2 = target.value; changeResultado() }">
      </div>

      <div class="col-md-3 d-flex align-items-center mt-2 mt-md-0">
        <select class="form-select" @input="({target}) => {estado.operadorAtual = target.value; changeResultado()}">
          <option value="+" selected>Soma</option>
          <option value="-">Subtração</option>
          <option value="*">Multiplicação</option>
          <option value="/">Divisão</option>
        </select>
      </div>
    </div>
  </form>
</template>