<script setup>
  import { ref } from 'vue';

  const nome = (ref(prompt("Informe seu nome:")));
  const idade = (ref(prompt("Informe sua idade:")));
  const contador = ref(0);

  function incrementar() {
    contador.value++;
  }

  function decrementar() {
    if (contador.value > 0) {
      contador.value--;
    }
  }

  function reiniciar() {
    contador.value = 0;
  }

  function inverterTextoEmMaiusculo(texto) {
    return texto.split('').reverse().join('').toUpperCase();
  }
</script>

<template>
  <div class="info">
    <h2>Informações</h2>
    <p>Nome: {{ nome }} </p>
    <p>Idade:{{ idade }} anos</p>
    <hr />
    <p>
      Para completar 50 anos faltam: {{ 50 - idade }} anos
    </p>
    <p>O nome tem {{ nome.length }}  caracteres</p>
    <p>
      O nome invertido em maiúscula é:{{
      inverterTextoEmMaiusculo(nome) }} 
    </p>
  </div>
  <br>
  <div class="contador">
    <h2>Contador</h2>
    <p>Valor: {{ contador }}</p>
    <button class="botao" @click="incrementar">Incrementar</button>
    <button class="botao" @click="decrementar">Decrementar</button>
    <button class="botao" @click="reiniciar">Reiniciar</button>
    <div
    >
      <p v-if="contador > 10">Valor maior que 10</p>
      <p v-else>Valor menor que 10</p>
    </div>
  </div>
</template>

<style scoped>
.info{
  background-color: #000000;
  text-align: center;
  font-size: 35px;
  color: white;
  border-radius: 50px;
  width: 280%;
  height: 500px;
  margin-bottom: 100%;
margin-left: -200px;}

.contador{
  margin-top: 100%;
  background-color: #000000;
  text-align: center;
  font-size: 35px;
  color: white;
  border-radius: 50px;
  width: 280%;
  height: 400px;
  margin-top: -90%;
  margin-left: -200px;}

  .botao{
    border-radius: 30px;
    width: 100px;

    


  }


  
</style>