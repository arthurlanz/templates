<script setup>
import { ref } from 'vue'

const nome = ref('Arthur');
const idade = ref(16);
const contador = ref(0)

function inverter(texto) {
  return texto.split('').reverse().join('').toUpperCase()
}

function incrementar() {
  contador.value++;
}
function decrementar() {
  contador.value--;
}
function reiniciar() {
  contador.value = 0;
}
</script>

<template>
  <div class="info">
    <h1>Exemplo 1 - Mostrando informações na tela</h1>
    <p>Nome: {{ nome }} </p>
    <p>Idade: {{ idade }} anos</p>
    <hr />
    <p>Para completar 50 anos faltam: {{ 50 - idade }} anos</p>
    <p>O nome tem {{ nome.length }} caracteres</p>
    <p>O nome invertido em letra maiúscula é: {{ inverter(nome) }} </p>
    <hr />
  </div>
  <div class="contador">
    <h2>Contador do Arthur</h2>
    <p>Valor: {{ contador }} </p>
    <button @click="incrementar">+</button>
    <button @click="decrementar">-</button>
    <button @click="reiniciar">Reiniciar</button>
    <div :style="{ backgroundColor: contador > 10 ? 'green' : 'red' }">
      <p v-if="contador > 10">Valor maior que 10</p>
      <p v-else>Valor menor que 10</p>
    </div>
  </div>

</template>

<style scoped>
.info,
.contador {
  background-color: rgb(255, 255, 255);
  padding: 20px 30px;
  color: rgb(10, 10, 10);
  border-radius: 10px;
}

h1 {
  color: rgb(12, 139, 0);
  font-weight: bold;
  font-size: 1.5em;
}

button {
  margin: 10px;
  padding: 10px;
  border: 0;
  border-radius: 5px;
  background-color: rgb(139, 224, 143);
  color: black;
  font-weight: bold;
  cursor: pointer;
}

button:hover {
  background-color: rgb(0, 255, 26);
}

div {
  margin: 10px 0;
  padding: 10px;
  border-radius: 5px;
  color: rgb(27, 25, 25);
  font-weight: bold;
}
</style>
